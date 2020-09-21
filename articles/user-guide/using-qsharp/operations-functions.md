---
title: 中的作業和函數 Q#
description: 如何定義和呼叫作業和函式，以及控制和 adjoint 作業特殊化。
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: e9a84de2753bc3293f441e66ee53e78559263e5c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833486"
---
# <a name="operations-and-functions-in-no-locq"></a>中的作業和函數 Q#

## <a name="defining-new-operations"></a>定義新的作業

作業是的核心 Q# 。
宣告之後，您可以從傳統的 .NET 應用程式呼叫它們，例如使用模擬器或內的其他作業 Q# 。
中定義的每個 Q# 作業都可以呼叫任何數目的其他作業，包括語言所定義的內建內建作業。 定義這些內建作業的特定方式 Q# 取決於目的電腦。
編譯時，每項作業都會表示為可提供給目的電腦的 .NET 類別類型。

每個原始程式檔 Q# 都可以定義任何數目的作業。
作業名稱在命名空間中必須是唯一的，且不能與類型或函式名稱衝突。

作業宣告由關鍵字組成 `operation` ，後面接著做為作業名稱的符號、定義作業引數的型別識別碼元組、冒號 `:` 、描述作業結果型別的型別批註、選擇性的注釋（具有作業特性）、左大括弧，以及作業宣告的主體（以大括弧括住） `{ }` 。

每個作業都會接受輸入、產生輸出，並指定一或多個作業特製化的實作為。
本文的不同章節將詳細說明可能的特製化，以及如何定義和呼叫它們。
現在，請考慮下列作業，此作業只會定義預設的本文特製化，並採用單一量子位作為其輸入，然後在該輸入上呼叫內建作業 <xref:microsoft.quantum.intrinsic.x> ：

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

關鍵字會 `operation` 開始作業定義，後面接著名稱，如下所示 `BitFlip` 。
接著，輸入的類型會定義 (`Qubit`) ，以及用來 `target` 參考新作業內之輸入的名稱。
最後， `Unit` 定義運算的輸出是空的。
`Unit` 的用法類似于 `void` c # 和其他命令式語言，相當於 `unit` F # 和其他功能性語言。

作業也會傳回比更有趣 `Unit` 的類型。
例如，此作業會傳回 <xref:microsoft.quantum.intrinsic.m> 類型的輸出 `Result` ，表示已執行度量。  您可以將作業從作業傳遞至另一個作業，或使用它搭配 `let` 關鍵字來定義新的變數。

這種方法可代表在低層級與量子作業互動的傳統計算，例如 [密集編碼](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding)：

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> 中的每個作業 Q# 都只會接受一個輸入，而且只會傳回一個輸出。
> 多個輸入和輸出是使用 *元組*表示，這會將多個值一起收集成單一值。
> 在這方面， Q# 是「元組即元組外」語言。
> 遵循這個概念之後，必須將一組空的括弧 `()` 視為具有類型的 "empty" 元組來讀取 `Unit` 。

## <a name="controlled-and-adjoint-operations"></a>控制和 Adjoint 作業

如果作業會執行單一轉換（如同中許多作業的情況），則 Q# 可以在 *adjointed* 或 *控制*時定義作業的運作方式。 作業的 *adjoint* 特製化會指定作業的「反轉」運作方式，而 *受控制* 的特製化則會指定當作業的應用程式在特定量子暫存器的狀態時，如何運作。

量子運算的伴隨對於許多方面來說非常重要。 如需與實用的程式設計技巧一起討論的其中一個這類情況的範例 Q# ，請參閱 [控制流程：動詞變化或是](xref:microsoft.quantum.guide.controlflow#conjugations)。 受控制的作業版本是一項新的作業，只有在所有控制項量子位都處於指定狀態時，才會有效地套用基底作業。
如果控制項量子位在迭加中，則會將基底作業時套用至迭加的適當部分。
因此，受控制的作業通常用來產生纏結。

當然， *控制的 adjoint* 特製化也可以存在，並指定作業 adjoint 的受控制應用程式。

> [!NOTE]
> 如果 $U $ 是作業所執行的單一轉換 `U` ，則 `Adjoint U` 表示單一轉換 $U ^ \dagger $，這是複雜的下轉型。
> 連續套用作業，然後將其 adjoint 狀態保持不變，如 $UU ^ \dagger = U ^ \dagger U = \id $、身分識別矩陣的事實所述。
> 控制作業的單一標記法稍微差別細微，不過您可以在量子運算概念找到更多詳細資料 [：多個量子位](xref:microsoft.quantum.concepts.multiple-qubits)。

下一節描述如何在程式碼中呼叫這些不同的特製化 Q# ，以及如何定義作業來支援它們。

### <a name="calling-operation-specializations"></a>呼叫作業特製化

中*functor*的仿函數 Q# 是用來從另一個作業定義新作業的 factory。
中的兩個標準函子 Q# 為 `Adjoint` 和 `Controlled` 。

在定義新作業的執行時，函子可以存取基底作業的執行。
因此，函子可以執行比傳統較高層級函數更複雜的函式。 函子沒有類型系統中的標記法 Q# 。 因此目前無法將它們系結至變數，或將它們傳遞為引數。 

將仿函數套用至作業（會傳回新的作業），以使用它。
例如，將仿函數套用至作業會傳回 `Adjoint` `Y` 新的作業 `Adjoint Y` 。 您可以叫用新的作業，就像任何其他作業一樣。
若要讓作業支援或函子的應用 `Adjoint` 程式 `Controlled` ，其傳回型別必須是 `Unit` 。 

#### <a name="adjoint-functor"></a>`Adjoint` 函

因此， `Adjoint Y(q1)` 會將仿函數套用至作業 `Adjoint` `Y` ，以產生新的作業，並將該新作業套用至 `q1` 。
新作業具有與基底作業相同的簽章和類型 `Y` 。
尤其是，新的作業也支援 `Adjoint` ，而且 `Controlled` 只有在基底作業執行時，才支援。
`Adjoint`仿函數本身是反向的，也就是， `Adjoint Adjoint Op` 一律與相同 `Op` 。

#### <a name="controlled-functor"></a>`Controlled` 函

同樣地，將 `Controlled X(controls, target)` 仿函數套用至作業 `Controlled` `X` 以產生新的作業，並將該新作業套用至 `controls` 和 `target` 。

> [!NOTE]
> 在中 Q# ，受控制的版本一律採用控制項量子位的陣列，且控制一律會根據 `PauliZ`) `One` 狀態、$ \ket $ 中計算 (的所有控制項量子位 {1} 。
> 藉由在受控制的作業之前將適當的單一作業套用至控制項量子位，然後在受控制的作業之後套用單一作業的反轉，就可以達到以其他狀態為基礎的控制。
> 例如，將作業套用 `X` 至控制作業前後的控制項量子位，會讓作業控制 `Zero` 該量子位的狀態 ($ \ket {0} $) ; `H` 會在狀態的控制項之前和之後套用作業 `PauliX` `One` ，也就是-1 eigenvalue of Pauli X，$ \ket {-} \mathrel{： =} ( \ket \ket \sqrt {0} {1}) / {2} $ 而非 `PauliZ` `One` 狀態。

指定作業運算式之後，您就可以使用仿函數來形成新的作業運算式 `Controlled` 。
新作業的簽章是以原始作業的簽章為基礎。
結果類型是相同的，但輸入類型是具有量子位陣列的兩個元組，其中會將控制項量子位 () s 做為第一個專案，並將原始作業的引數做為第二個元素。
新作業支援 `Controlled` ，而且只有在原始作業執行時，才會支援 `Adjoint` 。

如果原始作業只接受單一引數，則會在此處播放 [單一元組等價](xref:microsoft.quantum.guide.types) 。
例如， `Controlled X` 是作業的受控制版本 `X` 。 
`X` 有型別 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 有型別， `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` 因為單一元組相等，這與相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。

如果基底作業採用數個引數，請記得將受控制版本之作業的對應引數以括弧括住，以將它們轉換成元組。
例如， `Controlled Rz` 是作業的受控制版本 `Rz` 。 
`Rz` 有型別 `((Double, Qubit) => Unit is Adj + Ctl)` ，所以 `Controlled Rz` 有型別 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。
因此，將 `Controlled Rz(controls, (0.1, target))` 會是 `Controlled Rz` (記下) 周圍括弧的有效調用 `0.1, target` 。

另一個範例 `CNOT(control, target)` 是，可以實作為 `Controlled X([control], target)` 。 如果目標應該由兩個控制項量子位控制 (CCNOT) ，請使用 `Controlled X([control1, control2], target)` 語句。

#### `Controlled Adjoint` 

`Controlled`和 `Adjoint` 函子上，因此套用或時沒有任何差異 `Controlled Adjoint Op` `Adjoint Controlled Op` 。


## <a name="defining-controlled-and-adjoint-implementations"></a>定義受控和 Adjoint 的實作為

在上述範例中的第一個作業宣告中，會 `BitFlip` 分別使用簽章和來定義作業和 `DecodeSuperdense` `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` 。
例如 `DecodeSuperdense` ，它不是單一作業，因此不會有受控制的無法 adjoint 特製化 (回想這類作業傳回) 的相關需求 `Unit` 。
不過，只要 `BitFlip` 執行單一作業 <xref:microsoft.quantum.intrinsic.x> ，您就可以使用這兩個特殊化來定義它。

本節將詳細說明如何在您的作業宣告中包含特製化的存在 Q# ，因此讓它們能夠與或函子一起呼叫 `Adjoint` `Controlled` 。
如需有效或無效來宣告特定特製化的某些情況的詳細資訊，請參閱本文中有效定義特製化的 [狀況](#circumstances-for-validly-defining-specializations) 。

作業特性會定義您可以套用至宣告作業的函子種類，以及它們的作用。 這些特製化的存在可以宣告為作業簽章的一部分，特別是透過具有作業特性的注釋： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。
每個特製化的實際執行可以是 *隱含* 或 *明確* 定義。

### <a name="implicitly-specifying-implementations"></a>隱含指定實作為

在此情況下，作業宣告的主體只包含預設的實值。 例如：

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
在這種情況下，編譯器會自動產生每個這類隱含宣告特製化的對應執行，以 `Adjoint` 在 `Controlled` 使用或函子時執行。

因此，的呼叫 `Adjoint PrepareEntangledPair` 會導致編譯器執行的 adjoint `CNOT` ，然後是的 adjoint `H` 。
這些個別作業都是自我 adjoint，因此產生的作業 `Adjoint PrepareEntangledPair` 只會包含套用的 `CNOT(here, there)` 和 `H(here)` 。
因此，您可以使用這項功能 `DecodeSuperdense` ，利用的 adjoint `PrepareEntangledPair` 將纏結狀態轉換回 unentangled 對量子位，以更簡潔地的方式撰寫上述範例中的：

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

在宣告中具有作業特性的注釋，有助於確保編譯器會根據預設的執行自動產生其他特製化。 

設計與函子搭配使用的作業時，必須考慮幾個重要的限制。
最重要的是，使用任何其他作業的輸出值之作業的特製化， *無法* 由編譯器自動產生，因為這種方式不清楚如何在這類作業中重新排列語句，以取得相同的效果。

因此，明確指定各種不同的執行通常會很有用。

### <a name="explicitly-specifying-implementations"></a>明確指定實現

在編譯器無法產生執行的情況下，您可以明確指定它。 這類明確特製化宣告可以包含適當的 *世代* 指示詞或使用者定義的執行。
以下是完整的可能性範圍，以及一些明確特製化的範例。 


#### <a name="explicit-specialization-declarations"></a>明確特製化宣告

Q# 作業可以包含下列明確的特製化宣告：

- 特製 `body` 化會指定未套用任何函子之作業的執行。
- 特製 `adjoint` 化會指定套用仿函數的作業執行 `Adjoint` 。
- 特製 `controlled` 化會指定套用仿函數的作業執行 `Controlled` 。
- 特製 `controlled adjoint` 化會指定套用和函子的作業執行 `Adjoint` `Controlled` 。
  這種特製化也可以命名為 `adjoint controlled` ，因為這兩個函子的上一次。


作業特製化是由特製化標記 (例如， `body` 或 `adjoint`) 後面接著其中一個：

- 如下所述的明確宣告。
- 指示編譯器*如何*產生特製化*的指示詞*，其中一個：
  - `intrinsic`，表示目的電腦提供特製化。
  - `distribute`，搭配和特製化使用 `controlled` `controlled adjoint` 。
    搭配使用時 `controlled` ，表示編譯器應該套用至中的所有作業來計算特製化 `Controlled` `body` 。
    搭配使用時 `controlled adjoint` ，表示編譯器應該套用 `Controlled` 至特製化中的所有作業，以計算特製化 `adjoint` 。
  - `invert`，這表示編譯器應該藉由反轉來計算特製 `adjoint` 化 `body` ，例如反轉作業的順序，並將 adjoint 套用至每一個。
    搭配使用時 `adjoint controlled` ，表示編譯器應藉由反轉特製化來計算特製化 `controlled` 。
  - `self`，表示 adjoint 特製化與特製 `body` 化相同。
    使用對和特製化 `self` 是合法的 `adjoint` `adjoint controlled` 。
    若為，表示特製化與特製化 `adjoint controlled` `self` `adjoint controlled` 相同 `controlled` 。
  - `auto`，表示編譯器應該選取適當的指示詞以套用。
    您無法使用 `auto` 進行特製 `body` 化。

指示詞和 `auto` 全部都需要右半冒號 `;` 。
如果提供了的明確宣告，則指示詞 `auto` 會解析為下列產生的指示詞 `body` ：

- 特製 `adjoint` 化會根據指示詞產生 `invert` 。
- 特製 `controlled` 化會根據指示詞產生 `distribute` 。
- `adjoint controlled` `invert` 如果指定的明確宣告，而非的明確宣告，則會根據指示詞產生特製化 `controlled` `adjoint` ，否則會產生 `distribute` 。

> [!TIP]   
> 如果作業是自我 adjoint，請透過世代指示詞明確指定 adjoint 或受控制的 adjoint 特製化， `self` 以允許編譯器將該資訊用於優化用途。

包含使用者定義之實作為的特製化宣告包含引數元組，後面接著語句區塊和執行特製 Q# 化的程式碼。
在引數清單中， `...` 是用來表示整個作業所宣告的引數。
若為 `body` 和 `adjoint` ，引數清單應一律為 `(...)` ; 針對 `controlled` 和 `adjoint controlled` ，引數清單應該是表示控制項量子位陣列的符號，後面接著 `...` 以括弧括住; 例如 `(controls,...)` 。

### <a name="examples"></a>範例

作業宣告可能會像下面這樣簡單，定義基本 Pauli X 作業：

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
請注意，Pauli X 作業的 adjoint 是使用指示詞所定義， `self` 因為根據定義 `X` 是它自己的反向。

在先前的 `PrepareEntangledPair` 範例中，程式碼相當於下列包含明確特製化宣告的程式碼： 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
關鍵字 `auto` 表示編譯器應該決定如何產生特製化的實作為。

#### <a name="user-defined-specialization-implementation"></a>使用者定義的特製化實作為

如果編譯器無法自動產生特定特製化的執行，或可以指定更有效率的執行，則您可以手動定義執行。

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
在上述範例中， `adjoint invert;` 表示 adjoint 特製化是藉由反轉主體實作為產生的， `controlled adjoint invert;` 表示要藉由反轉受控制特製化的指定實來產生受控制的 adjoint 特製化。

如果有一或多個特製化（除了預設主體）必須明確宣告，則預設主體的實值也必須包裝到適當的特製化宣告中：

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>有效定義特製化的情況

#### <a name="operation-declarations-with-adjointcontrolled"></a>使用 adjoint/受控制的作業聲明

指定沒有 adjoint 或受控制版本的作業是合法的。 比方說，測量作業不是因為它們無法反轉或可控制。

如果作業的宣告 `Adjoint` 包含個別特製化的隱含或明確宣告，則作業支援和 `Controlled` 函子。

明確宣告的 adjoint/受控制特製化意指 adjoint/受控制特製化是否存在。 

若為主體包含重複直到成功迴圈、設定語句、測量、傳回語句或對不支援仿函數之其他作業的作業 `Adjoint` ，則無法在或指示詞之後自動產生 adjoint 特製化 `invert` `auto` 。

如果作業的主體包含不支援仿函數之其他作業的呼叫 `Controlled` ，就無法在或指示詞之後自動產生受控制的特製化 `distribute` `auto` 。

#### <a name="controlled-adjoint"></a>控制的 Adjoint

作業的受控制 adjoint 版本會指定如何執行該作業之 adjoint 的量子控制版本。
指定沒有受控制 adjoint 版本的作業是合法的，比方說，測量作業沒有控制的 adjoint 版本，因為它們都不是可控制的，也不能反轉。

如果只有 adjoint 和受控制的特製化存在，則作業的受控制 adjoint 特製化必須存在。 在此情況下，會推斷受控制 adjoint 特製化是否存在。 如果未明確定義任何實作，編譯會產生適當的特製化。

如果作業的主體包含其他沒有受控制 adjoint 版本之作業的呼叫， `invert` `distribute` 就不可能在、或指示詞之後自動產生 adjoint 特製化 `auto` 。


### <a name="type-compatibility"></a>類型相容性

在使用具有較少函子但相同簽章之作業的任何地方，使用具有其他函子支援的作業。 例如，在使用類型作業的任何地方使用類型的作業 `(Qubit => Unit is Adj)` `(Qubit => Unit)` 。

Q# 對可呼叫的傳回型別而言是 *協* 變數：傳回型別的可呼叫，與 `'A` 具有相同輸入類型的可呼叫相容，以及與相容的結果型別相容 `'A` 。

Q# 相對於輸入類型是 *逆變* 性：接受型別做為輸入的可呼叫，與 `'A` 具有相同結果型別和與相容的輸入類型的可呼叫相容 `'A` 。

亦即，假設有下列定義，

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

您可以

- `ConjugateInvertWith`使用 `inner` 或的引數叫用函數 `Invert` `ApplyUnitary` 。
- `ConjugateUnitaryWith`使用的引數叫用函數 `inner` `ApplyUnitary` ，但不叫用 `Invert` 。
- 從傳回型別的值 `(Qubit[] => Unit is Adj + Ctl)` `ConjugateInvertWith` 。

> [!IMPORTANT]
> Q# 0.3 在使用者自訂類型的行為上引進了顯著的差異。

使用者定義型別會被視為基礎型別的包裝版本，而不是做為子類型。
這表示，如果您預期基礎型別的值為，就無法使用使用者定義型別的值。


## <a name="defining-new-functions"></a>定義新函數

函式是純粹具決定性的傳統常式 Q# ，其與作業不同，因為它們不允許在計算輸出值之後產生任何影響。
尤其是，函數無法呼叫作業;act、配置或借用量子位;範例亂數字;或其他相依于函式的輸入值之外的狀態。
因此，函式 Q# 是 *純*虛擬的，因為它們一律會將相同的輸入值對應至相同的輸出值。
此行為可讓編譯器在產生作業特製化 Q# 時，安全地重新排列呼叫函式的方式和時機。

每個原始程式檔 Q# 都可以定義任何數目的函式。
函式名稱在命名空間中必須是唯一的，而且無法與作業或類型名稱衝突。

定義函式的運作方式類似于定義作業，但不能為函式定義任何 adjoint 或受控特製化。
例如：

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

或 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>函數中的傳統邏輯 = = 良好

只要有可能的話，就能以函式（而非作業）寫出傳統邏輯，讓作業可以更容易使用。 例如，如果您已撰寫先前的宣告 `Square` 做為作業*operation*，則編譯器無法保證以相同的輸入呼叫它會一致地產生相同的輸出。

若要底線函式和作業之間的差異，請考慮傳統方式從作業內取樣亂數字的問題 Q# ：

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

每次 `U` 呼叫時，會有不同的動作 `target` 。
尤其是，編譯器無法保證如果您將特製化宣告加入 `adjoint auto` 至 `U` ，則 `U(target); Adjoint U(target);` 會做為身分識別 (也就是無法運作的) 。
這違反了 [向量和矩陣](xref:microsoft.quantum.concepts.vectors)中定義之 adjoint 的定義，因此可讓編譯器在您呼叫作業的作業中自動產生 adjoint 特製化，以 <xref:microsoft.quantum.math.randomreal> 中斷編譯器所提供的保證; <xref:microsoft.quantum.math.randomreal> 是沒有 adjoint 或受控制版本存在的作業。

另一方面，允許等函式呼叫 `Square` 是安全的，並確保編譯器只需要保留輸入，以 `Square` 保持其輸出穩定。
因此，將盡可能多的傳統邏輯隔離到函式，可讓您輕鬆地在其他函數和作業中重複使用該邏輯。


## <a name="generic-type-parameterized-callables"></a>泛型 (類型參數化) Callables

您可能想要定義的許多函數和作業實際上不會依賴其輸入的類型，而只會透過其他函式或作業隱含地使用其類型。
例如，請考慮許多功能性語言通用的 *對應* 概念;假設函式 $f (x) $ 和值的集合 $ \{ x_1、x_2、\dots ..、x_n \} $、map 會傳回新的集合 $ \{ f (x_1) 、f (x_2) 、\dots ..、f (x_n \} $。
若要在中執行這項 Q# 功能，請利用函式是第一個類別的事實。
以下是在 `Map` `T` 您找出需要的型別時，使用做為預留位置的簡單範例。

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

請注意，無論您替代何種實際型別，此函式看起來非常類似。
例如，從整數到 Paulis 的對應，看起來與從浮點數到字串的對應很大：

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

基本上，您可以 `Map` 針對所遇到的每一組類型撰寫的版本，但這會帶來幾個難題。
比方說，如果您在中發現錯誤 `Map` ，則必須確保在所有版本的中都能一致地套用修正程式 `Map` 。
此外，如果您要建立新的元組或 UDT，您現在也必須同時建立新的 `Map` to go 以及新的類型。
雖然這是針對少數這類函式方便追蹤的，但當您收集更多和更多功能的相同表單時 `Map` ，引入新類型的成本會以相當短的順序過長大。

不過，這種困難的結果是因為您未提供編譯器所需的資訊，以辨識不同版本的 `Map` 相關資訊。
實際上，您希望編譯器將 `Map` 類型的數學函式視為某種 Q# *類型* 的數學函數 Q# 。

Q# 讓函式和作業具有 *型別參數*，以及它們的一般元組參數，以正規化這個概念。
在先前的範例中，您想要將 `Map` `Int, Pauli` 第一個案例和 `Double, String` 第二個案例中的型別參數視為有型別參數。
在大部分的情況下，請使用這些型別參數，就好像它們是一般型別一樣。 使用型別參數的值來建立陣列和元組、呼叫函數和作業，以及指派給一般或可變動變數。

> [!NOTE]
> 間接相依性最極端的情況是量子位，也就是 Q# 程式無法直接依賴型別的結構， `Qubit` 但 **必須** 將這類型別傳遞給其他作業和函式。

回到先前的範例，您會看到必須 `Map` 有型別參數，一個用來表示輸入，另一個代表 `fn` 輸出 `fn` 。
在中，這是藉由在宣告中的函式 Q# 或作業名稱後面加上角括弧 (，而 `<>` 非 brakets $ \braket {} $！ ) 來撰寫，並藉由列出每個類型參數。
每個類型參數的名稱都必須以刻度開頭 `'` ，表示它是型別參數，而不是一般型別 (也稱為 *實體* 型別) 。
因此， `Map` 會寫入：

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

請注意，的定義 `Map<'Input, 'Output>` 看起來非常類似于 previoius 版本。
唯一的差別在於您已明確通知編譯器，其 `Map` 不會直接相依于哪些 `'Input` 專案 `'Output` ，但可透過間接使用它們來處理任何兩種類型 `fn` 。
`Map<'Input, 'Output>`以這種方式定義之後，您就可以呼叫它，就好像它是一般的函式一樣：

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> 撰寫泛型函式和作業是一個位置，其中「元組-元組外」是一個非常實用的方法，可考慮函式 Q# 和作業。
> 由於每個函式只會接受一個輸入，而且只會傳回一個輸出，所以類型的輸入會 `'T -> 'U` 符合 *任何*函式 Q# 。
> 同樣地，您可以將任何作業傳遞至類型的輸入 `'T => 'U` 。

作為第二個範例，請考慮撰寫函數以傳回兩個其他函式組合的挑戰：

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

在這裡，您必須明確地指定 `A` 、 `B` 和是什麼， `C` 進而嚴格地限制新函式的公用程式 `Compose` 。
畢竟， `Compose` 只取決於 `A` 、和 `B` `C` *via* `innerFn` `outerFn` 。
或者，您可以將型別參數加入至， `Compose` 這表示它適用于 *任何* `A` 、 `B` 和 `C` ，只要這些參數符合和所預期的參數即可 `innerFn` `outerFn` ：

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q#標準程式庫提供一系列的類型參數化作業和函式，讓高階控制流程更容易表達。
這些將在[ Q# 標準程式庫指南](xref:microsoft.quantum.libraries.standard.intro)中進一步討論。


## <a name="callables-as-first-class-values"></a>Callables 為第一級值

使用函式（而非作業）來推理控制流程和傳統邏輯的一項重要技巧，是利用中的作業和函 Q# *式為第一類*。
亦即，它們本身就是語言中的每個值。
例如，以下是完全有效的程式 Q# 代碼，如果有一些間接的：

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

`ourH`前一個程式碼片段中的變數值接著是作業，如此一來， <xref:microsoft.quantum.intrinsic.h> 您就可以像任何其他作業一樣呼叫該值。
有了這項功能，您就可以撰寫作業，將作業當作輸入的一部分來執行，形成更高順序的控制流程概念。
比方說，您可能會想要「方形」作業，方法是將它套用至相同的目標量子位兩次。

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>從函式傳回作業

請務必強調，您也可以將作業當作輸出的一部分傳回，這樣您就可以將某些類型的傳統條件式邏輯隔離為傳統函式，以操作的形式傳回量副程式的描述。
簡單的範例，請考慮遙傳範例，在此範例中，接收兩位傳統訊息的合作物件需要使用訊息，將其量子位解碼為適當的傳送狀態。
您可以撰寫採用這兩個傳統位的函式，並傳回適當的解碼作業。

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

這個新函式確實是一個函式，如果您使用和相同的值來呼叫它， `hereBit` `thereBit` 就一定會取回相同的作業。
因此，此解碼器可以安全地在作業中執行，而不需要考慮解碼邏輯如何與不同作業特製化的定義互動。
也就是說，函式內的傳統邏輯是隔離的，保證編譯器可以使用 impunity 來重新排序函式呼叫，只要保留輸入即可。


## <a name="partial-application"></a>部分應用程式

您可以使用 *部分應用程式*來大幅增加傳回作業的函式，在此情況下，您可以提供一或多個部分的輸入給函數或作業，而不需要實際呼叫它。 在先前的 `ApplyTwice` 範例中，您可以指出您不想要立即指定應套用輸入作業的量子位：

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

在此情況下，本機變數會保存部分套用的作業 `twiceOp` `ApplyTwice(op, _)` ，其中 `_` 表示尚未指定的輸入部分。
當您 `twiceOp` 在下一行進行呼叫時，會以輸入的形式傳遞至部分套用的作業，並將輸入的其餘部分寫入至原始作業。
因此，先前的程式碼片段實際上與直接呼叫相同 `ApplyTwice(op, target)` ，請儲存您所引進的新區域變數，如此您就可以在提供輸入的某些部分時延遲呼叫。

由於已部分套用的作業在提供整個輸入之前，並不會實際呼叫，因此您可以安全地部分套用作業，即使是在函式內也一樣。

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

基本上，內的傳統邏輯 `SquareOperation` 可能更牽涉到許多，但它仍會與作業的其餘部分隔離，方法是編譯器可提供函數的保證。 Q#標準程式庫會在整個中使用這種方法，以量副程式可立即使用的方式來表示傳統控制流程。


## <a name="recursion"></a>遞迴

Q# callables 允許直接或間接遞迴。
也就是說，作業或函式可以呼叫本身，或呼叫另一個直接或間接呼叫可呼叫作業的調用。

使用遞迴有兩個重要的批註，不過：

- 在作業中使用遞迴可能會干擾某些優化。
  這項干擾可能會對演算法的執行時間產生顯著的影響。
- 在實際的量子裝置上執行時，堆疊空間可能會受到限制，因此深層遞迴可能會導致執行階段錯誤。
  尤其是， Q# 編譯器和執行時間不會識別並優化 tail 遞迴。

## <a name="next-steps"></a>後續步驟

深入瞭解中的 [變數](xref:microsoft.quantum.guide.variables) Q# 。