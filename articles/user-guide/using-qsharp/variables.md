---
title: 中的變數 Q#
description: 瞭解如何使用中的不同變數 Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
no-loc:
- Q#
- $$v
ms.openlocfilehash: bb87f36d3c9b7df195f64e85151e833d494ea945
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835871"
---
# <a name="variables-in-no-locq"></a>中的變數 Q#

Q# 區分可變和不可變的符號，或 *變數*（系結/指派給運算式）。
一般情況下，建議使用不可變的符號，因為它可讓編譯器執行更多的優化。

系結的左邊是由符號元組和運算式的右手邊所組成。

## <a name="immutable-variables"></a>不可變變數

您可以使用關鍵字，將任何類型的值指派 Q# 給變數，以便在作業或函式內重複使用 `let` 。 

不可變的系結是由關鍵字組成 `let` ，後面接著符號或符號元組、等號 `=` 、用來系結符號 () s 的運算式，以及終止分號。

例如：

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

這會將 Pauli 運算子的特定陣列指派給變數名稱 (或 "symbol" ) `measurementOperator` 。

> [!NOTE]
> 在上述範例中，不需要明確指定新變數的類型，因為語句右邊的運算式 `let` 是明確的，而編譯器會推斷正確的型別。 

使用定義 `let` 的變數是 *不可變*的，也就是說，一旦定義之後，就無法再以任何方式變更。
這可讓您進行數個有説明的優化作業，包括優化將變數重新排序以套用作業變異的傳統邏輯 `Adjoint` 。

## <a name="mutable-variables"></a>可變變數

作為使用建立變數的替代方式 `let` ， `mutable` 關鍵字會建立可變動的變數，該變數一開始是使用關鍵字來建立時 *可以* 重新綁定 `set` 。

稍後在程式碼中，您可以將宣告並系結為語句一部分的符號重新系結 `mutable` 至不同的值。 如果稍後在程式碼中重新系結符號，其類型不會變更，而且新系結的值必須與該類型相容。

### <a name="rebinding-of-mutable-symbols"></a>可變動符號的重新系結

您可以使用語句來重新系結可變變數 `set` 。
這種重新系結是由關鍵字組成 `set` ，後面接著符號或符號元組、等號 `=` 、用來重新系結符號 () s 的運算式，以及終止分號。

以下是一些重新系結語句技術的範例。

#### <a name="apply-and-reassign-statements"></a>Apply 和重新指派語句

`set`如果右手邊是由二元運算子的應用程式所組成，且結果是要重新綁定至運算子的左邊引數，則特定種類的語句（ *apply 和重新指派*語句）可提供便利的串連方式。 例如，套用至物件的

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
`counter`在迴圈的每個反復專案中遞增計數器的值 `for` 。 上述程式碼相當於 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

所有二元運算子都可以使用類似的語句，其中左邊的型別符合運算式型別。 這些語句提供簡單的方式來累積值。

例如，假設 `qubits` 是量子位的註冊：
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Update 和重新指派語句

右手邊的 [複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) 有類似的串連。
同樣地，使用者定義型別中的*命名專案*以及*陣列專案*也會有*更新和重新指派*語句。  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

在陣列的案例中， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 標準連結 Q# 庫提供了許多常見的陣列初始化和操作需求所需的工具，因此有助於避免在一開始就必須更新陣列專案。 

更新和重新指派語句會在需要時提供替代：

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

例如，您可以使用中所提供之陣列的程式庫工具， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 輕鬆地定義函式，以傳回類型的陣列， `Pauli` 其中索引處的 `i` 專案會採用指定的 `Pauli` 值，而所有其他專案則是 () 的身分識別 `PauliI` 。

以下是這類函式的兩個定義，而第二個則利用我們處置的工具。

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

與其逐一查看陣列中的每個索引，並有條件地將它設定為 `PauliI` 或指定 `pauli` ，您可以改為使用 `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 來建立 `PauliI` 類型的陣列，然後只傳回已在索引中變更特定值的複製和更新運算式 `location` ：

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>元組解構

除了指派單一變數之外，您還可以使用 `let` 和關鍵字（ `mutable` 或任何其他系結結構，例如-） `set` 將 [元組類型](xref:microsoft.quantum.guide.types#tuple-types)的內容解壓縮。
這種形式的指派是用來 *解構* 該元組的元素。

如果系結的右手邊是元組，則您可以在指派時解構該元組。
這類解構可以牽涉到嵌套的元組，而只要右邊的元組形狀與符號元組的形狀相容，任何完整或部分解構都有效。

例如：

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>系結範圍

一般而言，符號系結會移出範圍，並在發生的語句區塊結束時變成無法執行。
這項規則有兩個例外狀況：

- 迴圈的迴圈變數系結 `for` 是在 for 迴圈主體的範圍內，而不是在迴圈結束之後。
- 迴圈的三個部分 `repeat` / `until` (主體、測試和修復) 作為單一範圍，因此本文中系結的符號可在測試和修復中使用。

對於這兩種類型的迴圈，每個迴圈都會在它自己的範圍中執行，因此在稍後的階段中，不會提供來自較早傳遞的系結。
如需這些迴圈的詳細資訊，請參閱 [控制流程](xref:microsoft.quantum.guide.controlflow)。

內部區塊繼承外部區塊的符號系結。
您只能針對每個區塊系結一次符號;使用與範圍內的另一個符號相同的名稱來定義符號不合法 (沒有「遮蔽」 ) 。
以下是合法的序列：

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

及

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

但這是不合法的：

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

如下所示：

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a>後續步驟

瞭解如何[Working With Qubits](xref:microsoft.quantum.guide.qubits)在中使用量子位 Q# 。