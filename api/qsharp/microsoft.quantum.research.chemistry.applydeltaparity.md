---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700711"
---
# <a name="applydeltaparity-operation"></a><span data-ttu-id="1e716-102">ApplyDeltaParity 操作</span><span class="sxs-lookup"><span data-stu-id="1e716-102">ApplyDeltaParity operation</span></span>

<span data-ttu-id="1e716-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="1e716-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="1e716-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e716-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e716-105">計算上一個 PQRS 之間的同位檢查差異 .。。詞彙和下一個 PQRS .。。術語。</span><span class="sxs-lookup"><span data-stu-id="1e716-105">Computes difference in parity between a previous PQRS... terms and the next PQRS... term.</span></span> <span data-ttu-id="1e716-106">這項差異是在輔助量子位上計算。</span><span class="sxs-lookup"><span data-stu-id="1e716-106">This difference is computed on a auxiliary qubit.</span></span>

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1e716-107">輸入</span><span class="sxs-lookup"><span data-stu-id="1e716-107">Input</span></span>

### <a name="prevfermionicterm--int"></a><span data-ttu-id="1e716-108">prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1e716-108">prevFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1e716-109">先前 PQRS 的索引清單 .。。條款。</span><span class="sxs-lookup"><span data-stu-id="1e716-109">List of indices to previous PQRS... terms.</span></span>


### <a name="nextfermionicterm--int"></a><span data-ttu-id="1e716-110">nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1e716-110">nextFermionicTerm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1e716-111">下一個 PQRS 的索引清單 .。。條款。</span><span class="sxs-lookup"><span data-stu-id="1e716-111">List of indices to next PQRS... terms.</span></span>


### <a name="aux--qubit"></a><span data-ttu-id="1e716-112">aux： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1e716-112">aux : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1e716-113">儲存同位計算結果的輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="1e716-113">Auxiliary qubit onto which parity computation results are stored.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1e716-114">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1e716-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1e716-115">量子位依所有 PQRS 的動作 .。。條款。</span><span class="sxs-lookup"><span data-stu-id="1e716-115">Qubit acted on by all PQRS... terms.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e716-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e716-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1e716-117">備註</span><span class="sxs-lookup"><span data-stu-id="1e716-117">Remarks</span></span>

<span data-ttu-id="1e716-118">這會假設 P 的索引 < Q < R < S < .。。適用于 prevPQ 和 nextPQ。</span><span class="sxs-lookup"><span data-stu-id="1e716-118">This assumes that indices of P < Q < R < S < ... for both prevPQ and nextPQ.</span></span>