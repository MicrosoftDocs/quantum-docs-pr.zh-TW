---
title: Q 中的作業和函數#
description: 如何定義和呼叫作業和函式，以及受控制和 adjoint 的操作特製化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 9e924b973c4f22a59dd862df3f4f0d70278a1b4e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327793"
---
# <a name="operations-and-functions-in-q"></a>Q 中的作業和函數#

## <a name="defining-new-operations"></a>定義新的作業

作業是 Q # 的核心。
一旦宣告之後，您可以從傳統 .NET 應用程式（例如，使用模擬器），或由 Q # 中的其他作業呼叫。
在 Q # 中定義的每個作業都可以呼叫任何數目的其他作業，包括語言所定義的內建內建函式作業。 定義這些內部作業的特定方式取決於目的電腦。
在編譯時，每個作業都會表示為可提供給目的電腦的 .NET 類別類型。

每個 Q # 來源檔案都可以定義任何數目的作業。
作業名稱在命名空間中必須是唯一的，而且可能不會與類型或函式名稱衝突。

作業宣告包含關鍵字 `operation` ，後面接著是作業名稱的符號、定義作業引數的具類型識別碼元組、冒號 `:` 、描述作業結果類型的類型注釋、選擇性具有作業特性的注釋、左括弧、作業宣告 `{` 的主體，以及最後的右大括弧 `}` 。

每個作業都會接受輸入、產生輸出，並指定一或多個作業特製化的執行。
以下詳細說明可能的特製化，以及如何定義/呼叫它們。
現在，請考慮下列作業，這項作業只會定義預設的本文特製化，並以單一 qubit 作為其輸入，然後在該輸入上呼叫內建作業 <xref:microsoft.quantum.intrinsic.x> ：

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

關鍵字 `operation` 會開始作業定義，後面接著名稱; 此處為 `BitFlip` 。
接下來，輸入的類型會定義為 `Qubit` ，並使用名稱 `target` 來參考新作業中的輸入。
同樣地， `Unit` 會定義作業的輸出是空的。
這 `void` 在 c # 和其他命令式語言中的用法類似，相當於 `unit` F # 和其他功能性語言。

作業也會傳回比更有趣 `Unit` 的類型。
例如，作業會傳回 <xref:microsoft.quantum.intrinsic.m> 類型的輸出 `Result` ，表示已執行測量。 我們可以將作業的輸出傳遞至另一個作業，或可搭配 `let` 關鍵字來定義新的變數。

這可代表在較低層級與量子作業互動的傳統計算，例如[superdense 編碼](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)：

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
> Q # 中的每個作業都只接受一個輸入，並只傳回一個輸出。
> 接著會使用*元組*來表示多個輸入和輸出，這會將多個值一起收集成單一值。
> 非正式地說，問 # 是一種「元組輸出」語言。
> 遵循此概念之後， `()` 應該會讀取為具有類型的「空」元組 `Unit` 。


## <a name="controlled-and-adjoint-operations"></a>控制和 Adjoint 作業

如果作業會執行單一轉換，如同在 Q # 中的許多作業，則可以在*adjointed*或*控制*時定義操作的運作方式。 作業的*adjoint*特製化會指定作業的「反向」運作方式，而*受控制*的特製化則會指定作業在其應用程式以特定量子暫存器的狀態為條件時的運作方式。

量子運算的 Adjoints 對於量子計算的許多層面很重要。 接下來，在 [[動詞變化](#conjugations)] 區段中，您會發現其中一個這類情況會與有用的 Q # 程式設計技術一起討論。

作業的受控制版本是新的作業，只有在所有控制項 qubits 都處於指定的狀態時，才會有效地套用基底作業。
如果控制項 qubits 在重迭中，則會將基底作業套用 coherently 至重迭的適當部分。
因此，控制的作業通常用來產生會任何牽連。

當然，*控制的 adjoint*特製化也可能存在，指定受控制的作業 adjoint 應用程式。

> [!NOTE]
> 如果 $U $ 是作業所執行的單一轉換 `U` ，則 `Adjoint U` 代表單一轉換 $U ^ \dagger $，這是複雜的共軛轉型。
> 連續套用作業，然後其 adjoint 至狀態會使狀態保持不變，如 $UU ^ \dagger = U ^ \dagger U = \id $ （識別矩陣）的事實所示。
> 控制作業的單一標記法稍微差別細微，但您可以在量子計算概念中找到更多詳細資料[：多個 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。

下一節說明如何在您的 Q # 程式碼中呼叫這些特殊化。
在下面，我們將詳細說明如何定義作業來支援它們。

### <a name="calling-operation-specializations"></a>呼叫作業特製化

問 # 中的*仿函數*是從另一個作業定義新作業的 factory。
Q # 中的兩個標準函子為 `Adjoint` 和 `Controlled` 。

函子在定義新作業的執行時，可以存取基底作業的執行。
因此，函子可以執行比傳統更高層級函數更複雜的函式。 函子在 Q # 類型系統中沒有標記法。 因此目前無法將它們系結至變數，或將它們當做引數傳遞。 

仿函數的使用方式是將它套用至作業，並傳回新的作業。
例如，將仿函數套用至作業所產生的作業 `Adjoint` `Y` 會寫入為 `Adjoint Y` 。
接著就可以叫用新的作業，就像任何其他作業一樣。
如需支援和（或）函子之應用程式的作業 `Adjoint` `Controlled` ，其傳回型別必須是 `Unit` 。 

#### <a name="adjoint-functor"></a>`Adjoint`仿函數

因此， `Adjoint Y(q1)` 會將 Adjoint 仿函數套用至作業 `Y` ，以產生新的作業，並將該新作業套用至 `q1` 。
新作業的簽章和類型與基底作業相同 `Y` 。
特別是，新作業也會允許 `Adjoint` ，而且 `Controlled` 只有在基底作業執行時，才允許。
Adjoint 仿函數是它自己的反向;也就是， `Adjoint Adjoint Op` 一律與相同 `Op` 。

#### <a name="controlled-functor"></a>`Controlled`仿函數

同樣地， `Controlled X(controls, target)` 會將受控制的仿函數套用至作業， `X` 以產生新的作業，並將該新作業套用至 `controls` 和 `target` 。

> [!NOTE]
> 在 Q # 中，受控制的版本一律接受控制項 qubits 的陣列，而且指定的狀態一律會讓所有控制項 qubits 都處於計算（ `PauliZ` ） `One` 狀態，$ \ket {1} $。
> 藉由將適當的單一作業套用至受控制的作業之前的控制項 qubits，然後在受控制的作業之後套用單一作業的反轉，即可達成根據其他狀態進行控制。
> 例如，在 `X` 受控制的作業前後將作業套用至控制項 qubit，會導致作業控制 `Zero` 該 qubit 的狀態（$ \ket {0} $）; 在 `H` 之前和之後套用作業將會控制 `PauliX` `One` 狀態，也就是-1 eigenvalue of Pauli X，$ \ket {-} \mathrel{： =} （\ket {0} -\ket {1} ）/\sqrt {2} $，而不是 `PauliZ` `One` 狀態。

給定作業運算式時，可以使用仿函數來形成新的作業運算式 `Controlled` 。
新作業的簽章是以原始作業的簽章為基礎。
結果型別相同，但輸入型別是具有 qubit 陣列的兩個元組，其會將控制項 qubit 保存為第一個專案，並將原始運算的引數當做第二個元素。
新的作業支援 `Controlled` ，而且只有在原始作業執行時，才會支援 `Adjoint` 。

如果原始作業只接受單一引數，則會在這裡播放單一元組等價。
例如，是作業的 `Controlled X` 受控制版本 `X` 。 
`X`具有類型 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 具有類型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; 因為單一元組等價，所以這與相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。

如果基底作業接受數個引數，請記得將作業之受控制版本的對應引數括在括弧中，以將其轉換為元組。
例如，是作業的 `Controlled Rz` 受控制版本 `Rz` 。 
`Rz`具有類型 `((Double, Qubit) => Unit is Adj + Ctl)` ，因此 `Controlled Rz` 具有類型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。
因此，會 `Controlled Rz(controls, (0.1, target))` 是的有效調用 `Controlled Rz` （請注意周圍的括弧 `0.1, target` ）。

另一個範例 `CNOT(control, target)` 是，可以實作為 `Controlled X([control], target)` 。 如果目標應該由2個 control qubits （CCNOT）控制，我們可以使用 `Controlled X([control1, control2], target)` 語句。

#### `Controlled Adjoint` 

`Controlled`和 `Adjoint` 函子的上下班，因此套用或之間沒有任何 `Controlled Adjoint Op` 差異 `Adjoint Controlled Op` 。


## <a name="defining-controlled-and-adjoint-implementations"></a>定義受控制和 Adjoint 的實作為

在上述的第一個作業宣告範例中， `BitFlip` 會 `DecodeSuperdense` 分別使用簽章和來定義操作和 `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` 。
`DecodeSuperdense`包含測量，這不是單一作業，因此不會有任何受控制的 adjoint 特製化可能存在（請重新叫用這類作業傳回的相關需求 `Unit` ）。
不過，只要 `BitFlip` 執行單一作業 <xref:microsoft.quantum.intrinsic.x> ，我們就可以使用這兩個特殊化來定義它。

在這裡，我們會詳細說明如何在您的 Q # 作業宣告中包含特製化的存在性，因此讓他們能夠與 `Adjoint` 和/或函子一起呼叫 `Controlled` 。
接[下來，我們](#circumstances-for-validly-defining-specializations)將說明某些可能是有效或無效以宣告特定特製化的情況。

作業特性定義哪些類型的函子可套用至已宣告的作業，以及它們有何影響。 這些特製化的存在可以宣告為作業簽章的一部分，特別是透過具有作業特性的注釋： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。
每個特製化的實際執行方式可以是*隱含*或*明確*定義的。

### <a name="implicitly-specifying-implementations"></a>隱含指定實現

在此情況下，作業宣告的主體只會包含預設的實作為。 例如：

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
在這裡，編譯器會自動產生每個這類隱含宣告特製化的對應實作為，以在 `Adjoint` 使用或 `Controlled` 函子時執行。

因此，的呼叫 `Adjoint PrepareEntangledPair` 會導致編譯器先執行的 adjoint `CNOT` ，然後再進行的 adjoint `H` 。
這些個別的作業都是自我 adjoint，因此產生的作業 `Adjoint PrepareEntangledPair` 只會包含套用，然後才會套用 `CNOT(here, there)` `H(here)` 。
因此，我們可以使用這 `DecodeSuperdense` 項資訊來撰寫上述範例更簡潔地，方法是使用的 adjoint，將 `PrepareEntangledPair` 光子狀態轉換回 unentangled 對 qubits：

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

在宣告中具有作業特性的注釋，非常適合用來確保編譯器會根據預設執行自動產生其他特製化。 

設計要與函子搭配使用的作業時，有一些重要的限制需要考慮。
最重要的是，使用任何其他作業的輸出值之作業的特製化，*不能*由編譯器自動產生，因為在這類作業中重新排序語句以取得相同的效果並不明確。

因此，明確指定各種不同的執行通常會很有用。

### <a name="explicitly-specifying-implementations"></a>明確指定實現

如果編譯器無法產生執行，則可以明確指定。 這類明確特製化宣告可以包含適當的*世代*指示詞或使用者定義的實作為。
在這裡，我們提供了完整的各種可能性，範例如下所示。


#### <a name="explicit-specialization-declarations"></a>明確特製化宣告

Q # 作業可以包含下列明確的特製化宣告：

- 特製 `body` 化會指定未套用任何函子之作業的執行。
- 特製 `adjoint` 化會指定已套用仿函數之作業的執行 `Adjoint` 。
- 特製 `controlled` 化會指定已套用仿函數之作業的執行 `Controlled` 。
- 特製 `controlled adjoint` 化會指定同時套用和函子作業的執行 `Adjoint` `Controlled` 。
  這個特製化也可以命名為 `adjoint controlled` ，因為這兩個函子會向下。


作業特製化包含特製化標記（例如 `body` 或 `adjoint` 等等），後面接著下列其中一個：

- 明確宣告，如下所述。
- 指示編譯器*如何*產生特製化*的指示詞，這是*下列其中一個：
  - `intrinsic`，這表示特製化是由目的電腦所提供。
  - `distribute`，可與和特製化搭配 `controlled` 使用 `controlled adjoint` 。
    與搭配使用時 `controlled` ，它會指出編譯器應該藉由套用 `Controlled` 至中的所有作業來計算特製化 `body` 。
    與搭配使用時 `controlled adjoint` ，它會指出編譯器應該藉由套用至特製 `Controlled` 化中的所有作業來計算特製化 `adjoint` 。
  - `invert`，這表示編譯器應該藉由反轉來計算特製 `adjoint` 化 `body` ，亦即反轉作業順序，並將 adjoint 套用至每一個。
    與搭配使用時 `adjoint controlled` ，這表示編譯器應該藉由反轉特製化來計算特製化 `controlled` 。
  - `self`，表示 adjoint 特製化與特製 `body` 化相同。
    這對於和特製化而言是合法的 `adjoint` `adjoint controlled` 。
    針對 `adjoint controlled` ，表示特製化與特製化 `self` `adjoint controlled` 相同 `controlled` 。
  - `auto`，表示編譯器應該選取要套用的適當指示詞。
    `auto`不能用於特製 `body` 化。

指示詞和 `auto` 全部都需要結尾的分號 `;` 。
如果提供的明確宣告，指示詞 `auto` 會解析為下列產生指示詞 `body` ：

- 特製 `adjoint` 化是根據指示詞所產生 `invert` 。
- 特製 `controlled` 化是根據指示詞所產生 `distribute` 。
- `adjoint controlled` `invert` 如果指定了的明確宣告 `controlled` ，而不是針對，則會根據指示詞產生特製化 `adjoint` ， `distribute` 否則為。

> [!TIP]   
> 如果作業是自我 adjoint 的，請透過世代指示詞明確指定 adjoint 或受控制的 adjoint 特製化， `self` 以允許編譯器使用該資訊來進行優化。

包含使用者定義之實作為的特製化宣告，是由引數元組後面接著語句區塊，以及用來實行特製化的 Q # 程式碼所組成。
在引數清單中， `...` 是用來代表整個作業所宣告的引數。
針對 `body` 和 `adjoint` ，引數清單應一律為 `(...)` ; 針對 `controlled` 和 `adjoint controlled` ，引數清單應該是代表控制項 qubits 陣列的符號，後面接著 `...` 以括弧括住 `(controls,...)` ，例如。

### <a name="examples"></a>範例

作業宣告可能會像下面這樣簡單，其定義基本的 Pauli X 運算：

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
請注意，Pauli X 作業的 adjoint 是以指示詞定義， `self` 因為根據定義 `X` 是它自己的反向。

`PrepareEntangledPair`上述的程式碼相當於下列程式碼，其中包含明確的特製化宣告： 

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
關鍵字 `auto` 表示編譯器應該決定如何產生特製化執行。

#### <a name="user-defined-specialization-implementation"></a>使用者定義的特製化執行

如果編譯器無法自動產生特定特製化的實作為，或者可以指定更有效率的執行，則也可以手動定義執行。

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
在上述範例中， `adjoint invert;` 表示 adjoint 特製化是藉由將主體實作為反轉而產生，並 `controlled adjoint invert;` 指出受控制的 adjoint 特製化是藉由反轉所控制特製化的指定實作為而產生的。

如果需要明確宣告預設主體以外的一個或多個特製化，則預設主體的執行也必須包裝為適當的特製化宣告：

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

#### <a name="operation-declarations-with-adjointcontrolled"></a>具有 adjoint/受控的作業宣告

指定不含 adjoint 或受控制版本的作業是合法的。 比方說，測量作業並不是，因為它們不是可反轉或可以控制的。

如果作業的宣告 `Adjoint` 包含個別特製化的隱含或明確宣告，則作業支援和/或 `Controlled` 函子。

明確宣告的 adjoint/控制特製化意味著存在 adjoint/控制特製化。 

如果作業的主體包含重複執行迴圈、set 語句、量值、傳回語句，或呼叫不支援仿函數的其他作業 `Adjoint` ， `invert` `auto` 則不能在或指示詞之後自動產生 adjoint 特製化。

若作業的主體包含不支援仿函數的其他作業呼叫 `Controlled` ，就無法在或指示詞之後自動產生受控制的特製化 `distribute` `auto` 。

#### <a name="controlled-adjoint"></a>控制的 Adjoint

作業的受控制 adjoint 版本會指定如何實作為作業 adjoint 的配量控制版本。
指定沒有受控制 adjoint 版本的作業是合法的：比方說，測量作業沒有受控制的 adjoint 版本，因為它們都不是可控制也不可逆。

只有在 adjoint 和受控制的特製化都存在時，作業的受控制 adjoint 特製化才需要存在。 在這種情況下，系統會推斷受控制的 adjoint 特製化，而且編譯器會產生適當的特製化（如果未明確定義任何實作為）。 

若作業的內文包含的呼叫不具有受控制 adjoint 版本的其他作業， `invert` 則無法在、或指示詞之後自動產生 adjoint 特製化 `distribute` `auto` 。


### <a name="type-compatibility"></a>類型相容性

具有其他函子支援的作業可以在具有較少函子的作業中使用，但預期會有相同的簽章。
例如，類型的作業可以在 `(Qubit => Unit is Adj)` 預期為類型作業的任何位置使用 `(Qubit => Unit)` 。

Q # 是可呼叫傳回類型的*協*變數：傳回類型的可呼叫，與 `'A` 具有相同輸入類型和與相容之結果類型的可呼叫相容 `'A` 。

問 # 是相對於輸入類型的*逆變*性：接受類型做為輸入的可呼叫，與 `'A` 具有相同結果類型的可呼叫和與相容的輸入類型相容 `'A` 。

也就是，假設有下列定義：

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

下列為 true：

- 函數 `ConjugateInvertWith` 可以使用 `inner` 或的引數叫用 `Invert` `ApplyUnitary` 。
- 函數 `ConjugateUnitaryWith` 可以使用 `inner` 的引數來叫用 `ApplyUnitary` ，但不能叫用 `Invert` 。
- `(Qubit[] => Unit is Adj + Ctl)`可能會從傳回類型的值 `ConjugateInvertWith` 。

> [!IMPORTANT]
> 問 # 0.3 在使用者定義型別的行為上引進了顯著的差異。

使用者自訂類型會被視為基礎類型的包裝版本，而不是子類型。
這表示在預期基礎類型的值時，使用者自訂類型的值無法使用。


### <a name="conjugations"></a>動詞變化

相較于傳統的位，釋出配量記憶體會稍微複雜一點，因為如果 qubits 仍光子，則盲目重設 qubits 可能會對其餘的計算造成不想要的效果。 在釋放記憶體之前，適當地「復原」執行的計算，可以避免這種情況。 量子運算的常見模式如下： 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

從0.9 版開始，我們支援 conjugation 語句來執行上述轉換。 使用該語句，可以透過 `ApplyWith` 下列方式來執行作業：

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
如果外部和內部轉換無法立即當做作業使用，這類 conjugation 語句會變得更有用，但以多個語句所組成的區塊來描述會更方便。 

在區塊內定義的語句的反向轉換會由編譯器自動產生，並在套用區塊完成後執行。
因為任何用來做為內部區塊一部分的可變變數無法在套用區塊中重新系結，所以產生的轉換保證會是在區塊內的計算 adjoint。 


## <a name="defining-new-functions"></a>定義新函數

函式在 Q # 中純粹是具決定性的傳統常式，這與作業不同，因為它們不允許超出計算輸出值的任何效果。
特別是，函數無法呼叫作業;採取行動、配置或借用 qubits;範例亂數字;或以其他方式相依于函式的輸入值以外的狀態。
因此，Q # 函式是*單純*的，因為它們一律會將相同的輸入值對應到相同的輸出值。
這可讓 Q # 編譯器在產生作業特製化時，安全地重新排序呼叫函式的方式和時機。

每個 Q # 來源檔案可能會定義任意數目的函數。
函數名稱在命名空間中必須是唯一的，而且可能不會與作業或類型名稱衝突。

定義函式的運作方式類似于定義作業，不同之處在于無法為函式定義任何 adjoint 或受控特殊化。
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

只要能夠這麼做，就能以函式而非作業的形式寫出傳統邏輯，這會很有説明，可以更輕鬆地從作業中使用。
例如，如果我們將上述宣告撰寫 `Square` 為作業，則*operation*編譯器無法保證以相同的輸入呼叫它，會一致地產生相同的輸出。

若要以底線表示函式和作業之間的差異，請考慮傳統方式從 Q # 操作中取樣亂數字的問題：

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

每次 `U` 呼叫時，它會在上有不同的動作 `target` 。
特別的是，編譯器無法保證如果我們將特製化宣告加入 `adjoint auto` 至 `U` ，則 `U(target); Adjoint U(target);` 會做為身分識別（也就是不需要 op）。
這會違反我們在[向量和矩陣](xref:microsoft.quantum.concepts.vectors)中看到的 adjoint 定義，讓能夠在我們呼叫作業的作業中自動產生 adjoint 特製化，這 <xref:microsoft.quantum.math.randomreal> 會中斷編譯器所提供的保證; <xref:microsoft.quantum.math.randomreal> 是沒有 adjoint 或控制版本存在的作業。

另一方面，允許函式呼叫（例如） `Square` 是安全的，因為編譯器可以確保它只需要保留的輸入，才能 `Square` 保持其輸出穩定。
因此，將盡可能多的傳統邏輯隔離到函式，可讓您輕鬆地在其他函數和作業中重複使用該邏輯。


## <a name="generic-type-parameterized-callables"></a>泛型（型別參數化） Callables

我們可能會想要定義的許多函式和作業實際上並不會依賴其輸入的類型，而只會透過一些其他函式或運算，隱含地使用其類型。
例如，請考慮許多功能性語言通用的*地圖*概念;假設函數 $f （x） $ 和值 $ x_1 的集合 \{ ，x_2，\dots ..，x_n \} $，map 會傳回新的集合 $ \{ f （x_1）、f （x_2）、\dots ..、f （x_n） \} $。
若要在 Q # 中執行此功能，我們可以利用該函式是第一個類別。
讓我們寫出一個簡單的範例 `Map` ，使用★做為預留位置，同時瞭解我們所需的類型。

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

請注意，無論我們在什麼實際的型別中，此函式看起來都很相似。
例如，從整數到 Paulis 的對應，與從浮點數到字串的對應大致相同：

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

基本上，我們可以 `Map` 針對我們所遇到的每一對類型撰寫版本的，但這會造成一些問題。
比方說，如果我們在中發現錯誤 `Map` ，則必須確保在所有版本的中都已一致套用修正程式 `Map` 。
此外，如果我們要建立新的元組或 UDT，我們現在也必須建立新的 `Map` 來搭配新的型別。
雖然這是少數這類函式的方便追蹤，但我們會收集與相同表單的多個函式，而 `Map` 新類型的成本會以相當短的順序變得過長龐大。

不過，大部分的困難之處在于，我們尚未提供編譯器所需的資訊，來辨識不同版本的 `Map` 關聯。
實際上，我們希望編譯器將 `Map` q #*類型*中的某種數學函式視為 q # 函式。

這種概念的正規化方式是讓函式和作業具有*型別參數*，以及它們的一般元組參數。
在上述範例中，我們想要 `Map` `Int, Pauli` 在第一個案例和 `Double, String` 第二個案例中將類型參數視為。
在大部分的情況下，這些類型參數可以用來當做一般類型使用：我們會使用類型參數的值來建立陣列和元組、呼叫函數和作業，以及指派給一般或可變變數。

> [!NOTE]
> 間接相依性最極端的情況，就是 qubits，其中 Q # 程式無法直接依賴類型的結構 `Qubit` ，但**必須**將這類類型傳遞給其他作業和函式。

回到上述範例，我們可以看到我們需要 `Map` 有型別參數，一個用來表示的輸入， `fn` 另一個用來表示的輸出 `fn` 。
在 Q # 中，這是藉由在其宣告中的函式或作業名稱後面加上角括弧（也就是 `<>` 不是 brakets $ {} ！）來撰寫，並列出每個型別參數。
每個型別參數的名稱都必須以滴答開頭 `'` ，表示它是型別參數，而不是一般型別（也稱為*具體*型別）。
在 `Map` 中，我們會撰寫：

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

請注意，的定義 `Map<'Input, 'Output>` 看起來非常類似于之前寫出的版本。
唯一的差別在於，我們已明確告知編譯器，其 `Map` 不會直接相依于 `'Input` 和 `'Output` ，但可透過間接使用它們來處理任何兩種類型 `fn` 。
一旦 `Map<'Input, 'Output>` 以這種方式定義，我們就可以像一般函式一樣呼叫它：

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> 撰寫泛型函式和作業是一個位置，其中「元組元組輸出」是一種非常有用的方法，可以思考問 # 函式和作業。
> 因為每個函式只接受一個輸入，而且只會傳回一個輸出，所以類型的輸入會 `'T -> 'U` 符合*任何*Q # 函數。
> 同樣地，任何作業都可以傳遞至類型的輸入 `'T => 'U` 。

作為第二個範例，請考慮撰寫會傳回兩個其他函式之組合的函式的挑戰：

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

在這裡，我們必須確切地指定 `A` 、 `B` 和， `C` 因此會嚴重限制新函式的公用程式 `Compose` 。
畢竟， `Compose` 只取決於 `A` 、 `B` 和 `C` *via* `innerFn` `outerFn` 。
或者，我們可以將型別參數新增至，以 `Compose` 表示它適用于*任何* `A` 、 `B` 和 `C` ，只要這些參數符合和所預期的參數即可 `innerFn` `outerFn` ：

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q # 標準程式庫提供了這類類型參數化作業和函式的範圍，讓您更容易表達更高順序的控制流程。
這些會在[問答 # 標準程式庫指南](xref:microsoft.quantum.libraries.standard.intro)中進一步討論。


## <a name="callables-as-first-class-values"></a>Callables 為第一級值

使用函式而不是作業來推理控制流程和傳統邏輯的一項重要技巧，就是利用 Q # 中的作業和函*式是第一類*。
也就是說，它們是語言中的每個值本身的許可權。
例如，下列是完全有效的 Q # 程式碼，如果有一點間接：

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

`ourH`上述程式碼片段中的變數值是作業 <xref:microsoft.quantum.intrinsic.h> ，因此我們可以像任何其他作業一樣呼叫該值。
這可讓我們撰寫在其輸入過程中採取作業的作業，形成更高順序的控制流程概念。
比方說，我們可以想像一下，將作業套用到相同的目標 qubit 兩次，以「正方形」作業。

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>從函式傳回作業

我們強調，我們也可以將作業當做輸出的一部分傳回，讓我們可以將一些傳統條件式邏輯隔離為傳統函式，以作業的形式傳回量副程式的描述。
做為簡單的範例，請考慮 teleportation 範例，其中接收兩個傳統訊息的合作物件需要使用訊息，將其 qubit 解碼為適當的傳送狀態。
我們可以根據採用這兩個傳統位的函式撰寫此程式，並傳回適當的解碼作業。

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

這個新函式確實是一個函式，在此情況下，如果我們使用和相同的值來呼叫它 `hereBit` `thereBit` ，我們一律會取回相同的作業。
因此，可以安全地在作業內執行此解碼器，而不需考慮解碼邏輯如何與不同作業特製化的定義互動。
也就是，我們已將傳統邏輯隔離在函式內，並保證編譯器，只要保留輸入，函式呼叫就可以與 impunity 重新排序。


## <a name="partial-application"></a>部分應用程式

我們可以透過使用*部分應用程式*來傳回作業的函式執行更多動作，我們可以將輸入的一個或多個部分提供給函式或作業，而不需要實際呼叫它。 例如，若要重新叫 `ApplyTwice` 用上述範例，我們可以指出我們不想要對應套用輸入作業的 qubit 立即指定：

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

在此情況下，本機變數 `twiceOp` 會保存部分套用的作業 `ApplyTwice(op, _)` ，其中尚未指定的輸入部分會以表示 `_` 。
當我們 `twiceOp` 在下一行中實際呼叫時，會將輸入的所有剩餘部分當做原始作業傳遞給部分套用的作業。
因此，上述程式碼片段實際上與直接呼叫相同 `ApplyTwice(op, target)` ，因此我們引進了新的區域變數，讓我們能夠延遲呼叫，同時提供輸入的某些部分。

由於已部分套用的作業並不會實際被呼叫，直到提供了完整的輸入為止，我們也可以安全地從函式內部分套用作業。

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

原則上，中的傳統邏輯 `SquareOperation` 可能更牽涉到，但它仍會與作業的其餘部分隔離，因為編譯器可以提供關於函數的保證。
這種方法會在整個 Q # 標準程式庫中用來以可在量副程式中輕鬆使用的方式來表示傳統控制流程。


## <a name="recursion"></a>遞迴

Q # callables 允許直接或間接遞迴。
也就是說，作業或函式可能會呼叫本身，或呼叫可直接或間接呼叫可呼叫作業的其他調用。

使用遞迴有兩個重要的批註，不過：

- 在作業中使用遞迴可能會干擾特定的優化。
  這可能會對演算法的執行時間產生重大影響。
- 在實際的量子裝置上執行時，堆疊空間可能會受到限制，因此深度遞迴可能會導致執行階段錯誤。
  特別是，Q # 編譯器和執行時間不會識別並優化尾遞迴。

## <a name="next-steps"></a>下一步

瞭解 Q # 中的[變數](xref:microsoft.quantum.guide.variables)。