---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698151"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


假設有兩個作業，請判斷它們對所有輸入狀態的作用都相同。

此判斷提示是藉由檢查所有狀態的作業動作（$V _0 \otimes ... \otimes V_ {n-1} $）來執行，其中 $V _k $ 是其中一個狀態 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $ 和 $ \ket{i} $ (+ 1 Eigenstate Of Pauli Y 運算子) 。

此判斷提示會使用 $n $ 量子位，而且需要比較多個呼叫作業。

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

作業和操作的量子位 $n $ 數目 `givenU` `expectedU` 。


### <a name="givenu--qubit--unit"></a>givenU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

要檢查 $n $ 量子位上的作業。


### <a name="expectedu--qubit--unit-adj"></a>expectedU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

要與之比較 $n $ 量子位上的參考作業 `givenU` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

狀態 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $ 和 $ \ket{i} $ 的基礎是 Chuang-Nielsen 基礎，如、Chuang [ *、Nielsen*](https://arxiv.org/abs/quant-ph/9610001)。

## <a name="see-also"></a>另請參閱

- [AssertOperationsEqualReferenced。](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)