---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700718"
---
# <a name="preparechoistate-operation"></a>PrepareChoiState 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


針對給定的參考和目標暫存器上的指定作業，準備 Choi 對於– Jamiłkowski 狀態。

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="op--qubit--unit"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 

作業 $ \Lambda $，其 Choi 對於– Jamiłkowski 狀態 $J ( \Lambda) /2 ^ N $ 是要準備的，其中 $N $ 是作用所在的量子位數目 `op` 。


### <a name="reference--qubit"></a>參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

從 $ \ket{00\cdots 0} $ 狀態開始的量子位登錄，用來做為動作的參考 `op` 。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

一開始會在要套用的 $ \ket{00\cdots 0} $ 狀態中量子位的註冊 `op` 。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

量子進程的 Choi 對於– Jamiłkowski state $J ( \Lambda) $ 的定義為 $ $ \begin{align} J ( \Lambda) \mathrel{： =} ( \boldone \otimes \Lambda)  (| \boldone\rangle \! \rangle\langle \! \langle\boldone |) ，\end{align} $ $ where $ |X\rangle \! \rangle $ 是資料行堆疊慣例中矩陣 $X $ 的 *向量化* 。 學習此狀態的傳統描述，可提供 $ \Lambda $ 對任意輸入狀態採取影響的完整資訊，並形成 *量子流程 tomography* 的基礎。

## <a name="see-also"></a>另請參閱

- [PrepareChoiStateA。](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [PrepareChoiStateC。](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [PrepareChoiStateCA。](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)