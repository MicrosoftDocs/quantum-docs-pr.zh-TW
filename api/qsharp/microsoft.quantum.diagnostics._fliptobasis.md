---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: d46c42846066befafda2af22f7b6e861cb260c33
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831016"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="7894d-102">_flipToBasis 操作</span><span class="sxs-lookup"><span data-stu-id="7894d-102">_flipToBasis operation</span></span>

<span data-ttu-id="7894d-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7894d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7894d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7894d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7894d-105">將對應 $ \ket \otimes\cdots\ket $ 的 unitaries 套用 {0} {0} 至 $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $，其中 $ \ket{\ psi_k} $ 相依于 `basis[k]` 。</span><span class="sxs-lookup"><span data-stu-id="7894d-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="7894d-106">值 `basis[k]` 與 $ \ket{\ psi_k} $ 之間的對應如下：</span><span class="sxs-lookup"><span data-stu-id="7894d-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="7894d-107">`basis[k]=0` $ \rightarrow \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="7894d-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="7894d-108">`basis[k]=1` $ \rightarrow \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="7894d-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="7894d-109">`basis[k]=2` $ \rightarrow \ket{+} $。</span><span class="sxs-lookup"><span data-stu-id="7894d-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="7894d-110">`basis[k]=3` $ \rightarrow \ket{i} $ ( + 1 eigenstate of Pauli Y ) 。</span><span class="sxs-lookup"><span data-stu-id="7894d-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7894d-111">輸入</span><span class="sxs-lookup"><span data-stu-id="7894d-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="7894d-112">基礎： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7894d-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7894d-113">單一量子位基礎狀態識別碼的陣列 (0 <= 識別碼 <= 3) ，每個量子位元素各一個。</span><span class="sxs-lookup"><span data-stu-id="7894d-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="7894d-114">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7894d-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7894d-115">要在其上運作的量子位。</span><span class="sxs-lookup"><span data-stu-id="7894d-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7894d-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7894d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

