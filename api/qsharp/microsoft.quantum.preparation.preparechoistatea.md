---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateA
title: PrepareChoiStateA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with an adjoint variant onto given reference and target registers.
ms.openlocfilehash: c679f9a02aa15f9a582257770b8dc57d798d1b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697583"
---
# <a name="preparechoistatea-operation"></a>PrepareChoiStateA 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


針對給定的參考和目標暫存器上具有 adjoint 變異的指定作業，準備 Choi 對於– Jamiłkowski 狀態。

```qsharp
operation PrepareChoiStateA (op : (Qubit[] => Unit is Adj), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="op--qubit--unit-adj"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞




### <a name="reference--qubit"></a>參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [PrepareChoiState。](xref:Microsoft.Quantum.Preparation.PrepareChoiState)