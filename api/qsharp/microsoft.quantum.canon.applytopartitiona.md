---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: ApplyToPartitionA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 79f8fbed1592670031b3348155cdd4000eadc1fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208341"
---
# <a name="applytopartitiona-operation"></a><span data-ttu-id="e72d5-102">ApplyToPartitionA 操作</span><span class="sxs-lookup"><span data-stu-id="e72d5-102">ApplyToPartitionA operation</span></span>

<span data-ttu-id="e72d5-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e72d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e72d5-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e72d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e72d5-105">將一組作業套用至註冊的指定分割區分成兩個部分。</span><span class="sxs-lookup"><span data-stu-id="e72d5-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="e72d5-106">修飾詞 `A` 表示作業 adjointable。</span><span class="sxs-lookup"><span data-stu-id="e72d5-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="e72d5-107">輸入</span><span class="sxs-lookup"><span data-stu-id="e72d5-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="e72d5-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="e72d5-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e72d5-109">要套用至指定資料分割的作業配對。</span><span class="sxs-lookup"><span data-stu-id="e72d5-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="e72d5-110">numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e72d5-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e72d5-111">要放入資料分割第一個部分的目標量子位數目。</span><span class="sxs-lookup"><span data-stu-id="e72d5-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="e72d5-112">其餘的量子位會組成資料分割的第二個部分。</span><span class="sxs-lookup"><span data-stu-id="e72d5-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e72d5-113">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e72d5-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e72d5-114">由指定的兩項作業進行分割並操作的量子位登錄。</span><span class="sxs-lookup"><span data-stu-id="e72d5-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e72d5-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e72d5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e72d5-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e72d5-116">See Also</span></span>

- [<span data-ttu-id="e72d5-117">Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="e72d5-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)