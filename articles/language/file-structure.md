---
title: 檔案結構 |Microsoft Docs
description: 'Q # 檔案結構'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 40b2e7ddf5def6285250dffe130b152429dce1f8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185183"
---
# <a name="file-structure"></a>檔案結構

Q # 檔案是由一系列的命名空間宣告所組成。
每個命名空間宣告都包含使用者定義類型、作業和函式的宣告。
命名空間宣告可包含每個宣告類型的任意數目，並依任何順序。
唯一可以出現在命名空間宣告外的文字是批註。
特別是，命名空間的檔批註會在宣告之前。

## <a name="namespace-declarations"></a>命名空間宣告

問 # 檔案通常只會有一個命名空間宣告，但可能會有 none （而且是空的或只包含批註），或可能包含多個命名空間。
命名空間宣告不可以是嵌套的。

同一個命名空間可以宣告在一起編譯的多個 Q # 檔案中，只要沒有任何類型、作業或具有相同名稱的函式宣告即可。
特別是，在多個檔案的相同命名空間中定義相同的型別是不正確，即使宣告相同也是一樣。

命名空間宣告包含關鍵字 `namespace`，後面接著命名空間的名稱、左大括弧 `{`、命名空間中包含的宣告，以及 `}`的右大括弧。
命名空間名稱會遵循一或多個以句點分隔 `.`之合法符號序列的 .NET 模式。
例如，`MyQuantumStuff` 和 `Microsoft.Quantum.Canon` 都是有效的命名空間名稱。
依照慣例，命名空間名稱中的符號是大寫的，但這不是必要的。

宣告可能會以任何順序出現在命名空間宣告中。
在檔案中進一步宣告之類型或 callables 的參考會正確解析;型別、運算或函式宣告不需要在參考之前。

## <a name="open-directives"></a>Open 指示詞

在命名空間區塊內，`open` 指示詞可用來匯入特定命名空間中定義的所有類型和 callables，並依其不合格的名稱加以參考。 

這類 `open` 指示詞是由 `open` 關鍵字組成，後面接著要開啟的命名空間和結束的分號。

例如，

```qsharp
open Microsoft.Quantum.Canon;
```

（選擇性）可能會定義已開啟之命名空間的簡短名稱，讓來自該命名空間的所有元素都可以（和需要）以定義的簡短名稱限定。 這種簡短名稱的定義方式是在 `open` 指示詞中的分號前面加上關鍵字 `as` 後面接著所需的簡短名稱：

```qsharp
open Microsoft.Quantum.Math as Math;
```

所有的 `open` 指示詞都必須出現在命名空間區塊中的任何 `function`、`operation`或 `newtype` 宣告之前。
`open` 指示詞適用于檔案內的整個命名空間區塊。

## <a name="user-defined-type-declarations"></a>使用者定義型別宣告

問 # 提供一種方式，讓使用者宣告新的使用者定義型別，如[Q # 型別模型](xref:microsoft.quantum.language.type-model)一節中所述。
即使基底類型完全相同，使用者定義類型也是相異的。
特別是，兩個使用者自訂類型的值之間不會自動轉換，即使基礎類型相同也一樣。

使用者定義型別宣告包含關鍵字 `newtype`，後面接著使用者定義型別的名稱、`=`、有效的型別規格和終止的分號。

例如：

```qsharp
newtype PairOfInts = (Int, Int);
```

每個 Q # 來源檔案都可以宣告任何數目的使用者定義類型。
類型名稱在命名空間中必須是唯一的，而且可能不會與作業和函式名稱衝突。

無法定義使用者定義類型之間的迴圈相依性。 因此，不可能在 Q # 內進行遞迴類型。

## <a name="operation-declarations"></a>作業宣告

作業是 Q # 的核心，大致類似于其他語言的函式。
每個 Q # 來源檔案都可以定義任何數目的作業。

作業名稱在命名空間中必須是唯一的，而且可能不會與型別和函式名稱衝突。

作業宣告包含關鍵字 `operation`，後面接著是作業名稱的符號、定義作業引數的類型識別碼元組、冒號 `:`、描述作業結果類型的類型注釋、選擇性具有作業特性的注釋、左大括弧 `{`、作業宣告的主體，以及最後的右大括弧 `}`。

作業宣告的主體是由預設的實值或特製化清單所組成。
如果只需要明確指定預設主體特製化的執行，則可以在宣告中直接指定預設的實值。
在此情況下，在宣告中具有作業特性的注釋，有助於確保編譯器會根據預設的執行自動產生其他特製化。 

例如 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

作業特性定義哪些類型的函子可套用至已宣告的作業，以及它們有何影響。 如果作業會執行單一轉換，則可以定義作業在*adjointed*或*控制*時的運作方式。
這些特製化的存在可以宣告為作業簽章的一部分。 然後編譯器會產生每個這類隱含宣告特製化的對應執行。 在上述範例中，編譯器會產生 adjoint、受控制和受控制的 adjoint 特製化。 

如果編譯器無法產生執行，則可以明確指定。 這種明確的特製化宣告可以包含適當的世代指示詞，以清楚瞭解如何建立特定特製化，或使用者定義的實作為方式。 範例中 `PrepareEntangledPair` 的程式碼相當於下列程式碼，其中包含明確的特製化宣告： 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
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
如果編譯器無法產生特定特製化的實作為，而沒有進一步的指示（例如更精確的產生指示詞），或如果可以指定更有效率的執行，則也可以手動定義執行。

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

在上述範例中，`adjoint invert;` 指出 adjoint 特製化是藉由將主體實作為反轉而產生，`controlled adjoint invert;` 表示會藉由反轉指定的執行方式來產生受控制的 adjoint 特製化受控制的特製化。

若要支援 `Adjoint` 和/或 `Controlled` 仿函數之應用程式的作業，其傳回型別一定要 `Unit`。 


### <a name="explicit-specialization-declarations"></a>明確特製化宣告

Q # 作業可以包含下列明確的特製化宣告：

- `body` 特製化會指定未套用任何函子之作業的執行。
- `adjoint` 特製化會指定套用 `Adjoint` 仿函數之作業的執行。
- `controlled` 特製化會指定套用 `Controlled` 仿函數之作業的執行。
- `controlled adjoint` 特製化會指定套用 `Adjoint` 和 `Controlled` 函子的作業執行。
  此特製化也可以命名為 `adjoint controlled`，因為這兩個函子會向後。


作業特製化包含特製化標記（例如 `body`或 `adjoint`等），後面接著下列其中一個：

- 明確宣告，如下所述。
- 指示編譯器如何產生特製化的指示詞，這是下列其中一個：
  - `intrinsic`，表示特製化是由目的電腦所提供。
  - `distribute`，可與 `controlled` 和 `controlled adjoint` 特殊化搭配使用。
    與 `controlled`搭配使用時，它會指出編譯器應該藉由將 `Controlled` 套用至 `body`中的所有作業來計算特製化。
    與 `controlled adjoint`搭配使用時，它會指出編譯器應該藉由將 `Controlled` 套用至 `adjoint` 特製化中的所有作業來計算特製化。
  - `invert`，表示編譯器應該藉由反轉 `body`來計算 `adjoint` 特製化，亦即反轉作業的順序，並將 adjoint 套用至每一個。
    與 `adjoint controlled`搭配使用時，這表示編譯器應該藉由反轉 `controlled` 特製化來計算特製化。
  - `self`，表示 adjoint 特製化與 `body` 特製化相同。
    這對於 `adjoint` 和 `adjoint controlled` 特製化而言是合法的。
    針對 `adjoint controlled`，`self` 表示 `adjoint controlled` 特製化與 `controlled` 特製化相同。
  - `auto`，表示編譯器應該選取要套用的適當指示詞。
    `auto` 可能無法用於 `body` 特製化。

指示詞和 `auto` 都需要結尾的分號 `;`。
如果提供 `body` 的明確宣告，`auto` 指示詞會解析為下列層代指示詞：

- `adjoint` 特製化是根據指示詞 `invert`所產生。
- `controlled` 特製化是根據指示詞 `distribute`所產生。
- `adjoint controlled` 特製化是根據指示詞所產生 `invert` 如果指定了 `controlled` 的明確宣告，但不是 `adjoint`的宣告，則為，否則 `distribute`。

> [!TIP]   
> 如果作業是自行 adjoint 的，請透過產生指示詞明確指定 adjoint 或受控制的 adjoint 特製化 `self`，讓編譯器能夠使用該資訊來進行優化。

包含使用者定義之實作為的特製化宣告，是由引數元組後面接著語句區塊，以及用來實行特製化的 Q # 程式碼所組成。
在引數清單中，`...` 是用來代表為整個作業所宣告的引數。
對於 `body` 和 `adjoint`而言，引數清單應一律 `(...)`;對於 `controlled` 和 `adjoint controlled`，引數清單應該是代表控制項 qubits 陣列的符號，後面接著 `...`，並以括弧括住;例如，`(controls,...)`。

如果需要明確宣告預設主體以外的一個或多個特製化，則預設主體的執行也必須包裝為適當的特製化宣告：

```qsharp
operation CountOnes(qs: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (q in qs) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Adjoint

作業的 adjoint 會指定如何實作為運算的複雜共軛轉置，也就是「反向執行」時作業的運作方式。
指定不含 adjoint 的作業是合法的;例如，量測作業沒有 adjoint，因為它們無法反轉。
如果作業的宣告包含 adjoint 特製化的隱含或明確宣告，則作業支援 `Adjoint` 仿函數。
明確宣告的受控制 adjoint 特製化表示 adjoint 特製化的存在。 

對於本文包含重複執行迴圈、set 語句、量值、傳回語句或不支援 `Adjoint` 仿函數之其他作業的呼叫，請在 `invert` 之後自動產生 adjoint 特製化，或 @no__不可能 t_2_ 指示詞。

### <a name="controlled"></a>管理

作業的受控制版本會指定如何實作用配量控制版本的作業，亦即作業在配量暫存器的狀態下套用時的運作方式。
[[控制](xref:microsoft.quantum.language.type-model#controlled)] 區段中會提供更完整的描述。

指定沒有受控制版本的作業是合法的：例如，測量作業沒有受控制的版本，因為它們無法控制。
作業只有在其宣告包含受控制特製化的隱含或明確宣告時，才支援 `Controlled` 仿函數。
明確宣告的受控制 adjoint 特製化表示已控制特製化的存在。 

對於本文包含不支援 `Controlled` 仿函數之其他作業的呼叫，不可能在 `distribute` 或 `auto` 指示詞之後自動產生受控制的特製化。

### <a name="controlled-adjoint"></a>控制的 Adjoint

作業的受控制 adjoint 版本會指定如何實作為作業 adjoint 的配量控制版本。
指定沒有受控制 adjoint 版本的作業是合法的：比方說，測量作業沒有受控制的 adjoint 版本，因為它們都不是可控制也不可逆。

只有在 adjoint 和受控制的特製化都存在時，作業的受控制 adjoint 特製化才需要存在。 在這種情況下，系統會推斷受控制的 adjoint 特製化，而且編譯器會產生適當的特製化（如果未明確定義任何實作為）。 

若作業的內文包含的呼叫不具有受控制 adjoint 版本的其他作業，則不能在 `invert`之後自動產生 adjoint 特製化，`distribute` 或 `auto` 指示詞。


### <a name="examples"></a>範例

作業宣告可能會像下面這樣簡單，其定義基本的 Pauli X 運算：

```qsharp
operation X (q : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

以下定義了「傳送」作業。

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>函式宣告

函式在 Q # 中純粹是傳統的常式。
每個 Q # 來源檔案可能會定義任意數目的函數。

函式宣告包含關鍵字 `function`，後面接著是函式名稱的符號、具類型的識別碼元組、描述函數傳回類型的類型注釋，以及描述其執行的語句區塊。函數.

定義函式的語句區塊必須括在 `{` 中，而 `}` 就像任何其他語句區塊一樣。

函數名稱在命名空間中必須是唯一的，而且可能不會與作業和類型名稱衝突。
函式可能不會配置或借用 qubits，或呼叫作業。 作業的部分應用，或傳遞操作類型的值是正常的。

例如，

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
