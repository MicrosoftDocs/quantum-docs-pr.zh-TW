---
title: 中的控制流程Q#
description: 迴圈、條件等。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: fc619d64bfebfc27d7feac6dafb2dd4cf22825d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867942"
---
# <a name="control-flow-in-no-locq"></a>中的控制流程Q#

在作業或函式中，每個語句會依序執行，類似于其他常見的命令式傳統語言。
不過，您可以用三種不同的方式修改控制流程：

* `if`報表
* `for`環回
* `repeat-until-success`環回

`if`和 `for` 控制流程結構會以熟悉的方式進行大部分的傳統程式設計語言。 [`Repeat-until-success`](#repeat-until-success-loop)本文稍後會討論迴圈。

重要的 `for` 是，迴圈和 `if` 語句可以用於自動產生[特殊化](xref:microsoft.quantum.guide.operationsfunctions)的作業。 在該案例中，迴圈的 adjoint `for` 會反轉方向，並接受每個反復專案的 adjoint。
此動作會遵循「鞋與 socks」原則：如果您想要復原並加上「鞋」，您必須先復原鞋，然後再復原「socks」。 

## <a name="if-else-if-else"></a>如果為，則為，否則為。

`if`語句支援條件式執行。
其中包含關鍵字 `if` 、括弧中的布林運算式，以及 (_then_區塊) 的語句區塊。
或者，任何數目的 else if 子句可以跟著遵循，其中每一個都包含關鍵字 `elif` 、括弧中的布林運算式，以及 (_else-if_區塊) 的語句區塊。
最後，語句可以選擇性地完成 else 子句，其中包含關鍵字， `else` 後面接著另一個語句區塊 (_else_區塊) 。

`if`條件會進行評估，如果為*true*，則會執行*then*區塊。
如果條件為*false*，則會評估第一個 else if 條件;如果為 true，則會執行*else-if*區塊。
否則，第二個 [if] 區塊會評估，然後是第三個，直到出現具有 true 條件的子句，或沒有其他的 if 子句為止。
如果原始*if*條件和所有 else if 子句評估為*false*，則會執行*else*區塊（如果有提供的話）。

請注意，不論是哪一種區塊執行，它都會在自己的範圍內執行。
`if` `elif` `else` 區塊結束之後，不會顯示在、或區塊內所做的系結。

例如

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
語句包含關鍵字 `for` ，後面接著符號或符號元組、關鍵字 `in` ，以及類型 `Range` 或陣列的運算式、全部在括弧中，以及語句區塊。

語句區塊 (迴圈的主體，) 重複執行，並以定義的符號 (迴圈變數) 系結至範圍或陣列中的每個值。
請注意，如果範圍運算式評估為空白範圍或陣列，則不會執行主體。
在進入迴圈之前，會完整評估運算式，而且在執行迴圈時不會變更。

迴圈變數會系結至迴圈主體的每個進入，並在主體結尾處解除系結。
在 for 迴圈完成之後，迴圈變數不會系結。
迴圈變數的系結是不可變的，並遵循與其他變數系結相同的規則。 

在這些範例中，是 qubits 的暫存器 `qubits` ，也就是) 類型的 (。 `Qubit[]` 

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

請注意，我們在結尾使用了算術左移的二元運算子 `<<<` 。 如需詳細資訊，請參閱[數值運算式](xref:microsoft.quantum.guide.expressions#numeric-expressions)。

## <a name="repeat-until-success-loop"></a>重複直到-成功迴圈

此 Q# 語言可讓傳統控制流程相依于測量 qubits 的結果。
這項功能可讓您執行功能強大的概率小工具，以降低執行 unitaries 的計算成本。
這種情況的範例是 (ru) 模式的*重複直到成功為止* Q# 。
這些 ru 模式是概率的程式，在基本閘道方面具有*預期*的低成本;產生的成本取決於實際執行，以及多個可能分支的交錯。

為了協助重複執行-成功 (ru) 模式， Q# 支援結構

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
迴圈主體會執行，然後評估條件。
如果條件為 true，則表示語句已完成;否則，會執行修復，而且語句會從迴圈主體開始再次執行。

Ru 迴圈的全部三個部分 (主體、測試和修復) 會被視為*每個重複*的單一範圍，因此，在本文中系結的符號會同時在測試和修復中提供。
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

如需更多範例和詳細資料，請參閱本文中的[重複執行-成功範例](#repeat-until-success-examples)。

> [!TIP]   
> 避免在函式內使用重複-成功迴圈。 使用*while*迴圈來提供函式內的對應功能。 

## <a name="while-loop"></a>While 迴圈

重複直到-成功模式具有非常量子特定的含意。 它們廣泛用於特定的量子演算法類別中，因此是中的專用語言結構 Q# 。 不過，根據條件中斷的迴圈，在編譯時期，其執行長度會是未知的，會在量子執行時間中特別小心處理。 不過，它們在函式中的用法是 unproblematic 的，因為這些迴圈只包含在傳統 (非量子) 硬體上執行的程式碼。 

Q#因此，只支援在函式內使用 while 迴圈。 `while`語句包含關鍵字 `while` 、括弧中的布林運算式，以及語句區塊。
語句區塊 (迴圈的主體) 執行，只要條件評估為 `true` 。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a>Return 陳述式

Return 語句會結束作業或函數的執行，並將值傳回給呼叫者。
其中包含關鍵字 `return` ，後面接著適當類型的運算式和結束分號。

例如
```qsharp
return 1;
```
或
```qsharp
return (results, qubits);
```

* 可呼叫的會傳回空的元組，不 `()` 需要 return 語句。
* 若要指定從作業或函式提早結束，請使用 `return ();` 。
傳回任何其他類型的 Callables 都需要最終傳回語句。
* 作業中沒有 return 語句的最大數目。
如果語句在區塊內遵循 return 語句，則編譯器可能會發出警告。

   
## <a name="fail-statement"></a>Fail 語句

Fail 語句會結束作業的執行，並將錯誤值傳回給呼叫者。
其中包含關鍵字 `fail` ，後面接著字串和結尾的分號。
語句會將字串傳回給傳統驅動程式，做為錯誤訊息。

作業內的 fail 語句數目沒有任何限制。
如果語句在區塊內遵循 fail 語句，則編譯器可能會發出警告。

例如

```qsharp
fail $"Impossible state reached";
```
或者，使用[字串插值](xref:microsoft.quantum.guide.expressions#interpolated-strings)，
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>重複執行-成功範例

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>適用于無理軸之單一 qubit 旋轉的 ru 模式 

在典型的使用案例中，下列作業會針對 Q# Bloch 球體上的無理軸 $ (I + 2I Z) /\sqrt {5} $ 執行旋轉。 此實作為使用已知的 ru 模式：

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>具有範圍內可變變數的 ru 迴圈

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

此範例顯示不含修復步驟的 ru 迴圈。 此程式碼是使用和閘道執行重要旋轉閘道 $V _3 = ( \boldone + 2 i Z) /\sqrt $ 的概率電路 {5} `H` `T` 。
迴圈會平均終止于 $ \frac {8} {5} $ 重複。
如需更多詳細資料，請參閱 qubit unitaries (Paetznick 和 Svore，2014) 的[*重複直到成功：非決定性分解*](https://arxiv.org/abs/1311.1074)。

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

最後，以下是 {1} {3} {2} {0} {1} 從 $ \ket +} $ 狀態開始準備量子 state $ \frac {\sqrt} \left ( \sqrt \ket + \right \ket{) $ 的 ru 模式範例。

這項作業所顯示的重要程式設計功能包括：

* `fixup`迴圈中更複雜的部分，牽涉到量子作業。 
* 使用 `AssertMeasurementProbability` 語句來確定在程式中特定點測量量子狀態的機率。

如需和作業的詳細資訊 [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) ，請參閱[測試和調試](xref:microsoft.quantum.guide.testingdebugging)程式。

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

如需詳細資訊，請參閱[標準程式庫提供的單元測試範例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：

## <a name="next-steps"></a>後續步驟

瞭解中的[測試和調試](xref:microsoft.quantum.guide.testingdebugging) Q# 。
