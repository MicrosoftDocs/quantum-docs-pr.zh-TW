---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225749"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="0cf5c-102">ApplyDeltaParity 操作</span><span class="sxs-lookup"><span data-stu-id="0cf5c-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="0cf5c-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="0cf5c-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="0cf5c-104">封裝： [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry) ......... 化學</span><span class="sxs-lookup"><span data-stu-id="0cf5c-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="0cf5c-105">計算上一個 PQRS 之間的同位檢查差異 .。。詞彙和下一個 PQRS .。。術語。</span><span class="sxs-lookup"><span data-stu-id="0cf5c-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="0cf5c-106">這項差異是在輔助量子位上計算。</span><span class="sxs-lookup"><span data-stu-id="0cf5c-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0cf5c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="0cf5c-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="0cf5c-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0cf5c-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0cf5c-109">先前 PQRS 的索引清單 .。。條款。</span><span class="sxs-lookup"><span data-stu-id="0cf5c-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="0cf5c-110">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0cf5c-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0cf5c-111">下一個 PQRS 的索引清單 .。。條款。</span><span class="sxs-lookup"><span data-stu-id="0cf5c-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="0cf5c-112">aux： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0cf5c-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0cf5c-113">儲存同位計算結果的輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="0cf5c-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="0cf5c-114">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0cf5c-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0cf5c-115">量子位依所有 PQRS 的動作 .。。條款。</span><span class="sxs-lookup"><span data-stu-id="0cf5c-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0cf5c-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cf5c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0cf5c-117">備註</span><span class="sxs-lookup"><span data-stu-id="0cf5c-117">Remarks</span></span>

<span data-ttu-id="0cf5c-118">這會假設 P 的索引 < Q < R < S < .。。適用于 prevPQ 和 nextPQ。</span><span class="sxs-lookup"><span data-stu-id="0cf5c-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>