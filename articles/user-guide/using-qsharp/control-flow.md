---
title: Q 中的控制流程#
description: 迴圈、條件等。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: c534e016fcb8b50e66c11ca29c253ba0512acc6e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430946"
---
# <a name="control-flow-in-q"></a>Q 中的控制流程#

在作業或函式內，每個語句會依序執行，類似于最常見的命令式傳統語言。
不過，您可以透過三種不同的方式修改這個控制流程：

- `if`報表
- `for`環回
- `repeat`-`until`環回

我們會延遲對後者的討論，[如下所示](#repeat-until-success-loop)。
`if` `for` 不過，和控制流程結構的處理方式，對大部分的傳統程式設計語言而言都很熟悉。

重要的 `for` 是，迴圈和 `if` 語句甚至可以用於自動產生特殊化的作業。 在此情況下，迴圈的 adjoint `for` 會反轉方向，並接受每個反復專案的 adjoint。
這會遵循「鞋與 socks」原則：如果您想要復原並加上「鞋」，您必須先復原鞋，然後再復原「socks」。
如果您還在戴鞋，也能讓您更輕鬆地嘗試並將您的 socks 轉成由於！

## <a name="if-else-if-else"></a>如果為，則為，否則為。

`if`語句支援條件式執行。
其中包含關鍵字 `if` 、左括弧 `(` 、布林運算式、右括弧 `)` 和語句區塊（ _then_區塊）。
這後面可能接著任意數目的 else if 子句，其中每個都包含關鍵字 `elif` 、左括弧 `(` 、布林運算式、右括弧 `)` 和語句區塊（ _else-if_區塊）。
最後，語句可能會選擇性地以 else 子句完成，其中包含關鍵字， `else` 後面接著另一個語句區塊（ _else_區塊）。

`if`條件會進行評估，如果為 true，則會執行 then 區塊。
如果條件為 false，則會評估第一個 else if 條件;如果是 true，則為，否則為。
否則，會先測試第二個 [if] 區塊，然後再進行第三個，直到出現具有 true 條件的子句，或沒有其他的 if 子句為止。
如果原始 if 條件和所有 else if 子句評估為 false，則會執行 else 區塊（如果有提供的話）。

請注意，執行的任何區塊會在其本身的範圍中執行。
在、或區塊內所做的系 `if` 結，在 `elif` `else` 其結尾之後不會顯示。

例如，

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
或
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>For 迴圈

`for`語句支援在整數範圍或陣列上反覆運算。
語句包含關鍵字 `for` 、左括弧 `(` ，後面接著符號或符號元組、關鍵字 `in` 、型別 `Range` 或陣列的運算式、右括弧 `)` 和語句區塊。

語句區塊（迴圈的主體）會重複執行，其中已定義的符號（迴圈變數）會系結至範圍或陣列中的每個值。
請注意，如果範圍運算式評估為空的範圍或陣列，則完全不會執行主體。
在進入迴圈之前，會完整評估運算式，而且在執行迴圈時不會變更。

迴圈變數會系結至迴圈主體的每個進入，並在主體結尾處解除系結。
特別是，在 for 迴圈完成之後，迴圈變數不會系結。
宣告之符號的系結是不可變的，並遵循與其他變數系結相同的規則。 

在某些範例中，假設是 qubits 的暫存器 `qubits` （即類型的 `Qubit[]` ）， 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
請注意，我們在結尾使用了算術左移的二元運算子， `<<<` 以及可以在[數值運算式](xref:microsoft.quantum.guide.expressions#numeric-expressions)中找到的詳細資料。


## <a name="repeat-until-success-loop"></a>重複直到-成功迴圈

Q # 語言可讓傳統控制流程相依于測量 qubits 的結果。
這項功能可讓您執行功能強大的概率小工具，以降低執行 unitaries 的計算成本。
例如，在 Q # 中執行所謂的*重複-成功*（ru）模式是很容易的。
這些 ru 模式是概率的程式，在基本閘道方面具有*預期*的低成本，但真正的成本取決於實際執行，以及各種可能分支的實際交錯。

為了協助重複執行-成功（ru）模式，Q # 支援結構

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

其中 `expression` 是評估為類型值的任何有效運算式 `Bool` 。
執行迴圈主體，然後評估條件。
如果條件為 true，則表示語句已完成;否則，會執行修復，並從迴圈主體開始重新執行語句。

重複/結束迴圈的全部三個部分（主體、測試和修復）都會被視為*每個重複*的單一範圍，因此本文中系結的符號會在測試和修復中提供。
不過，完成修復的執行會結束語句的範圍，因此在本文或修復期間所做的符號系結，無法用於後續的重複。

此外，此 `fixup` 語句通常很有用，但不一定是必要的。
在不需要的情況下，結構
```qsharp
repeat {
    // do stuff
}
until (expression);
```
也是有效的 ru 模式。

在此頁面底部，我們會提供一些 ru[迴圈的範例](#repeat-until-success-examples)。

> [!TIP]   
> 避免在函式內使用重複-成功迴圈。 對應的功能是由函式中的迴圈所提供。 

## <a name="while-loop"></a>While 迴圈

重複直到-成功模式具有非常量子特定的含意。 它們廣泛用於特定的量子演算法類別中，因此是 Q # 中的專用語言結構。 不過，根據條件中斷的迴圈，在編譯時期，其執行長度會是未知的，需要在量子執行時間中特別小心處理。 另一方面，它們在函式中的用法是 unproblematic，因為這些只包含將在傳統（非量子）硬體上執行的程式碼。 

問 # 因此僅支援在函式內使用 while 迴圈。 `while`語句是由關鍵字 `while` 、左括弧 `(` 、條件（亦即布林運算式）、右括弧 `)` 和語句區塊所組成。
只要條件評估為，就會執行語句區塊（迴圈的主體） `true` 。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Return 陳述式

Return 語句會結束執行作業或函數，並將值傳回給呼叫者。
其中包含關鍵字 `return` ，後面接著適當類型的運算式和結束分號。

可呼叫的會傳回空的元組，不 `()` 需要 return 語句。
如果需要提早結束， `return ()` 可以在此案例中使用。
傳回任何其他類型的 Callables 都需要最終傳回語句。

作業中沒有 return 語句的最大數目。
如果語句在區塊內遵循 return 語句，則編譯器可能會發出警告。

例如，
```qsharp
return 1;
```
或
```qsharp
return ();
```
或
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Fail 語句

Fail 語句會結束執行作業，並將錯誤值傳回給呼叫者。
其中包含關鍵字 `fail` ，後面接著字串和結尾的分號。
字串會傳回給傳統驅動程式，做為錯誤訊息。

作業內的 fail 語句數目沒有任何限制。
如果語句在區塊內遵循 fail 語句，則編譯器可能會發出警告。

例如，
```qsharp
fail $"Impossible state reached";
```
或者，使用[字串插值](xref:microsoft.quantum.guide.expressions#interpolated-strings)，
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>重複執行-成功範例

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>適用于無理軸之單一 qubit 旋轉的 ru 模式 

在典型的使用案例中，下列 Q # 作業會在 Bloch 球體上，針對 $ （I + 2i Z）/\sqrt $ 的無理軸執行旋轉 {5} 。 這是使用已知的 ru 模式來完成：

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a>範圍內具有可變變數的 ru 迴圈

這個範例示範如何使用可變動的變數， `finished` 這是在整個重複執行-修復迴圈的範圍內，而且會在迴圈之前初始化，並在修復步驟中更新。

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>不含的 ru`fixup`

例如，下列程式碼是使用和閘道 $V _3 = （\boldone + 2 i Z）/\sqrt $ 執行重要旋轉閘道的概率電路 {5} `H` `T` 。
迴圈會平均終止于 $ \frac {8} {5} $ 重複。
如需詳細資訊，請參閱[*重複直到成功：單一 qubit unitaries 的非決定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>用來準備量子狀態的 ru

最後，我們會顯示一個 ru 模式範例，以準備量子 state $ \frac {1} {\sqrt {3} } \left （\sqrt {2} \ket {0} + \ket {1} \right） $ （從 $ \ket{+} $ 狀態開始）。
另請參閱[標準程式庫所提供的單元測試範例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

這項作業中所顯示的重要程式設計功能，是迴圈中更複雜 `fixup` 的部分，其中牽涉到配量作業，並使用 `AssertProb` 語句來確定在程式中特定點測量量子狀態的機率。
如需和作業的詳細資訊，另請參閱[測試和調試](xref:microsoft.quantum.guide.testingdebugging)程式 [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) 。


## <a name="whats-next"></a>下一步
瞭解如何在 Q # 中進行[測試和調試](xref:microsoft.quantum.guide.testingdebugging)。