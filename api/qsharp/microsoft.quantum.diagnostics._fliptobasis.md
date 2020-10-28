---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: e074ed2ae259f6aef49a8d327ce518a9e2caebfa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698202"
---
# <a name="_fliptobasis-operation"></a>_flipToBasis 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


將對應 $ \ket \otimes\cdots\ket $ 的 unitaries 套用 {0} {0} 至 $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $，其中 $ \ket{\ psi_k} $ 相依于 `basis[k]` 。

值 `basis[k]` 與 $ \ket{\ psi_k} $ 之間的對應如下：

- `basis[k]=0` $ \rightarrow \ket {0} $。
- `basis[k]=1` $ \rightarrow \ket {1} $。
- `basis[k]=2` $ \rightarrow \ket{+} $。
- `basis[k]=3` $ \rightarrow \ket{i} $ ( + 1 eigenstate of Pauli Y ) 。

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="basis--int"></a>基礎： [Int](xref:microsoft.quantum.lang-ref.int)[]

單一量子位基礎狀態識別碼的陣列 (0 <= 識別碼 <= 3) ，每個量子位元素各一個。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要在其上運作的量子位。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

