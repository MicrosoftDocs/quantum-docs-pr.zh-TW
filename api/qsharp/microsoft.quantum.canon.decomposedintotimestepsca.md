---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699044"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


傳回對指定作業執行 Trotter – Suzuki 整合器的作業。

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="nsteps--int"></a>nSteps： [Int](xref:microsoft.quantum.lang-ref.int)

要分解為時間步驟的作業數目。


### <a name="op--intdoublet--unit-adj--ctl"></a>op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

一種作業，可接受索引輸入 (類型 `Int`) 和時間輸入 (類型 `Double`) 以進行分解。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

選取要使用的 Trotter-Suzuki 整合器順序。
Order 1 甚至訂單2，4，6,.。。目前支援。



## <a name="output--doublet--unit-adj--ctl"></a>輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

傳回實 Trotter – Suzuki 整合器的單一參數，其中第一個參數 `Double` 是整合步驟的大小，而第二個參數則是採取動作的目標。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

每次步驟應採取的型別;通常是 `Qubit[]` 或 `Qubit` 。

## <a name="remarks"></a>備註

以等於的呼叫時 `order` `1` ，此函式會傳回可由最低順序的 Trotter – Suzuki 整合者 $ $ \begin{align} S_1 ( \lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda} 的運算 \end{align} $ $，我們已遵循 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) 的標記法，並讓 $ \lambda $ 成為所傳回作業的第一個輸入所表示的演進時間 () ，並讓 let $ \{ H_j \} _ {j = 1} ^ {m} $ 成為一組 (扭曲-Hermitian) 要整合的 dynamical 產生器，這 `op(j, lambda, _)` 是由單一運算子 $e ^ {H_j \lambda} $ 所模擬。

同樣地， `order` 的會傳回 `2` 第二個順序的對稱 Trotter – Suzuki 整合者 $ $ \begin{align} S_2 ( \lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}。
\end{align} $ $

更高的值 `order` 會使用 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)的遞迴結構來執行。

## <a name="references"></a>參考

- [*D. Berry、G. Ahokas、Cleve、b. Sanders*](https://arxiv.org/abs/quant-ph/0508139)