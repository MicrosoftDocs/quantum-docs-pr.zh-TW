---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210568"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="8246d-102">PrepareChoiState 操作</span><span class="sxs-lookup"><span data-stu-id="8246d-102">PrepareChoiState operation</span></span>

<span data-ttu-id="8246d-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8246d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8246d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8246d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8246d-105">針對給定的參考和目標暫存器上的指定作業，準備 Choi 對於– Jamiołkowski 狀態。</span><span class="sxs-lookup"><span data-stu-id="8246d-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8246d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="8246d-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="8246d-107">op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8246d-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8246d-108">作業 $ \Lambda $，其 Choi 對於– Jamiołkowski 狀態 $J ( \Lambda) /2 ^ N $ 是要準備的，其中 $N $ 是作用所在的量子位數目 `op` 。</span><span class="sxs-lookup"><span data-stu-id="8246d-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="8246d-109">參考： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8246d-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8246d-110">從 $ \ket{00\cdots 0} $ 狀態開始的量子位登錄，用來做為動作的參考 `op` 。</span><span class="sxs-lookup"><span data-stu-id="8246d-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8246d-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8246d-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8246d-112">一開始會在要套用的 $ \ket{00\cdots 0} $ 狀態中量子位的註冊 `op` 。</span><span class="sxs-lookup"><span data-stu-id="8246d-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8246d-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8246d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8246d-114">備註</span><span class="sxs-lookup"><span data-stu-id="8246d-114">Remarks</span></span>

<span data-ttu-id="8246d-115">量子進程的 Choi 對於– Jamiłkowski state $J ( \Lambda) $ 的定義為 $ $ \begin{align} J ( \Lambda) \mathrel{： =} ( \boldone \otimes \Lambda)  (| \boldone\rangle \! \rangle\langle \! \langle\boldone |) ，\end{align} $ $ where $ |X\rangle \! \rangle $ 是資料行堆疊慣例中矩陣 $X $ 的 *向量化* 。</span><span class="sxs-lookup"><span data-stu-id="8246d-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="8246d-116">學習此狀態的傳統描述，可提供 $ \Lambda $ 對任意輸入狀態採取影響的完整資訊，並形成 *量子流程 tomography* 的基礎。</span><span class="sxs-lookup"><span data-stu-id="8246d-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="8246d-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8246d-117">See Also</span></span>

- [<span data-ttu-id="8246d-118">PrepareChoiStateA。</span><span class="sxs-lookup"><span data-stu-id="8246d-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="8246d-119">PrepareChoiStateC。</span><span class="sxs-lookup"><span data-stu-id="8246d-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="8246d-120">PrepareChoiStateCA。</span><span class="sxs-lookup"><span data-stu-id="8246d-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)