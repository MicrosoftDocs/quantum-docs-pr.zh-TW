---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: f36bccb727bb38a0cdf4f1fedabc9f3f554059ab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208392"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="fd7a6-102">ApplyToPartition 操作</span><span class="sxs-lookup"><span data-stu-id="fd7a6-102">ApplyToPartition operation</span></span>

<span data-ttu-id="fd7a6-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fd7a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fd7a6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd7a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd7a6-105">將一組作業套用至註冊的指定分割區分成兩個部分。</span><span class="sxs-lookup"><span data-stu-id="fd7a6-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="fd7a6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fd7a6-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="fd7a6-107">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd7a6-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fd7a6-108">要套用至指定資料分割的作業配對。</span><span class="sxs-lookup"><span data-stu-id="fd7a6-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="fd7a6-109">numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd7a6-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd7a6-110">要放入資料分割第一個部分的目標量子位數目。</span><span class="sxs-lookup"><span data-stu-id="fd7a6-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="fd7a6-111">其餘的量子位會組成資料分割的第二個部分。</span><span class="sxs-lookup"><span data-stu-id="fd7a6-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="fd7a6-112">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fd7a6-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fd7a6-113">由指定的兩項作業進行分割並操作的量子位登錄。</span><span class="sxs-lookup"><span data-stu-id="fd7a6-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd7a6-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd7a6-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fd7a6-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fd7a6-115">See Also</span></span>

- [<span data-ttu-id="fd7a6-116">Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="fd7a6-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="fd7a6-117">Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="fd7a6-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="fd7a6-118">Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="fd7a6-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)