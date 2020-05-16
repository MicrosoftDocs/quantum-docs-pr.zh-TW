---
title: Q 中的變數#
description: 填滿描述
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430895"
---
# <a name="variables-in-q"></a>Q 中的變數#

Q # 區分可變和不可變的符號，或「變數」（已系結/指派給運算式）。
一般來說，我們鼓勵使用不可變的符號，因為它可讓編譯器執行更多的優化。

系結的左邊是由符號元組和運算式的右手邊所組成。

## <a name="immutable-variables"></a>不可變的變數

您可以使用關鍵字，將 Q # 中任何類型的值指派給變數，以便在作業或函式內重複使用 `let` 。

不可變的系結包含關鍵字 `let` ，後面接著符號或符號元組、等號 `=` 、用來系結符號的運算式，以及終止的分號。

例如：

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

這會將特定的 Pauli 運算子陣列指派給變數名稱（或「符號」） `measurementOperator` 。

> [!NOTE]
> 我們不需要明確指定新變數的類型，因為語句右邊的運算式 `let` 是明確的，而且該類型是由編譯器推斷。 

使用定義的變數 `let` 是*不可變*的，這表示一旦定義後，就無法再以任何方式變更。
這可提供數個有用的優化，包括優化要重新排序之變數的傳統邏輯，以套用作業的 `Adjoint` 變體。

## <a name="mutable-variables"></a>可變變數

做為使用建立變數的替代方法 `let` ， `mutable` 關鍵字會建立一開始使用關鍵字建立之後，*可以*重新系結的可變變數 `set` 。

宣告和系結為語句一部分的符號， `mutable` 可能會在稍後的程式碼中重新系結至不同的值。 如果稍後在程式碼中重新系結符號，它的類型不會變更，且新系結的值必須與該類型相容。

### <a name="rebinding-of-mutable-symbols"></a>可變動符號的重新系結

可以使用語句重新系結可變變數 `set` 。
這類重新系結包含關鍵字 `set` ，後面接著符號或符號元組、等號、將符號重新系結 `=` 至的運算式，以及終止的分號。

在這裡，我們提供一些可能的重新系結語句技術範例

### <a name="apply-and-reassign-statements"></a>Apply-重新指派語句

`set`如果右側是由二元運算子的應用程式所組成，而結果是要重新系結至運算子的左引數，則我們稱之為*apply 和-重新指派*語句的特定種類語句可提供便利的串連方式。 例如，
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

所有二元運算子都有類似的語句，其中左邊的型別符合運算式型別。 這提供了一個簡單的方式來累積值的範例。

例如，假設 `qubits` 是 qubits 的 regsiter：
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>Update-重新指派語句

右手邊的[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)會有類似的串連。
同樣地，使用者定義型別中的*命名專案*以及*陣列專案*的*更新和重新指派*語句也會存在。  

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

在陣列的案例中， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 我們的標準程式庫會針對許多常見的陣列初始化和操作需求提供必要的工具，因此可協助避免必須先更新陣列專案。 

Update-重新指派語句會在需要時提供替代方法：

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

例如，針對中提供的陣列使用程式庫工具， [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 我們可以輕鬆地定義函式，以傳回 Paulis 的陣列，其中 Pauli at 索引會 `i` 採用指定的值，而所有其他專案都是身分識別。

以下是這類函式的兩個定義，第二個則利用我們的處置工具。

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

我們不會逐一查看陣列中的每個索引，並有條件地將它設定為 `PauliI` 或，因此， `Pauli` 我們可以改為使用 `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) 來建立 `PauliI` 的陣列，然後只傳回已在索引處變更特定值的複製和更新運算式 `location` ：

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>元組解構

除了指派單一變數之外， `let` 和 `mutable` 關鍵字---或事實上任何其他系結結構，例如 `set` （如下所述）---也允許將[元組類型](xref:microsoft.quantum.guide.types#tuple-types)的內容解壓縮。
這個表單的指派是用來*解構*該元組的元素。

如果系結的右手邊是元組，則該元組在指派時可能會解構。
這類解構可能牽涉到嵌套的元組，只要右側元組的形狀與符號元組的形狀相容，任何完整或部分解構都是有效的。

例如：

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>系結範圍

一般而言，符號系結會超出範圍，而且會在其發生的語句區塊結尾處變成無法執行。
這項規則有兩個例外狀況：

- 迴圈之迴圈變數的系結 `for` 是在 for 迴圈主體的範圍內，而不是在迴圈結束之後。
- 迴圈的所有三個部分 `repeat` / `until` （主體、測試和修復）都會被視為單一範圍，因此本文中系結的符號會在測試和修復中提供。

對於這兩種類型的迴圈，每次通過迴圈都會在其本身的範圍中執行，因此在稍後的階段中，不會提供來自較早階段的系結。
如需這些迴圈的詳細資訊，請參閱[控制流程](xref:microsoft.quantum.guide.controlflow)。

內部區塊會繼承外部區塊的符號系結。
符號只能系結每個區塊一次;定義符號的名稱與範圍內的另一個符號（不是「遮蔽」）並不合法。
下列順序會是合法的：

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

但這不合法：

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

## <a name="whats-next"></a>下一步
瞭解如何在 Q # 中使用[Qubits](xref:microsoft.quantum.guide.qubits) 。