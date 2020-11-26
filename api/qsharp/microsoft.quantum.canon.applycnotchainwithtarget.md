---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: 8ec85ce5805b3bbd1e1f7c739f27de3a861bc79e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219102"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="a9d85-102">ApplyCNOTChainWithTarget 操作</span><span class="sxs-lookup"><span data-stu-id="a9d85-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="a9d85-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a9d85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a9d85-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9d85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9d85-105">將量子位陣列的同位計算為目標量子位。</span><span class="sxs-lookup"><span data-stu-id="a9d85-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a9d85-106">描述</span><span class="sxs-lookup"><span data-stu-id="a9d85-106">Description</span></span>

<span data-ttu-id="a9d85-107">如果陣列一開始是處於 state $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{target}}} $，則最終狀態是由 $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{target}}} $。</span><span class="sxs-lookup"><span data-stu-id="a9d85-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="a9d85-108">輸入</span><span class="sxs-lookup"><span data-stu-id="a9d85-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="a9d85-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a9d85-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a9d85-110">計算同位的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="a9d85-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="a9d85-111">targetQubit： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a9d85-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a9d85-112">' 量子位 ' 的同位檢查進行 xor 的最終量子位。</span><span class="sxs-lookup"><span data-stu-id="a9d85-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9d85-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9d85-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a9d85-114">備註</span><span class="sxs-lookup"><span data-stu-id="a9d85-114">Remarks</span></span>

<span data-ttu-id="a9d85-115">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="a9d85-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="a9d85-116">及</span><span class="sxs-lookup"><span data-stu-id="a9d85-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```