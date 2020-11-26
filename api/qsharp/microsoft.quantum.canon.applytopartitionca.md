---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: ApplyToPartitionCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: b33670a91af5cbf280fdda0e57ddbbf8c9013e91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208292"
---
# <a name="applytopartitionca-operation"></a><span data-ttu-id="a1106-102">ApplyToPartitionCA 操作</span><span class="sxs-lookup"><span data-stu-id="a1106-102">ApplyToPartitionCA operation</span></span>

<span data-ttu-id="a1106-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a1106-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a1106-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1106-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1106-105">將一組作業套用至註冊的指定分割區分成兩個部分。</span><span class="sxs-lookup"><span data-stu-id="a1106-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="a1106-106">修飾詞 `CA` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="a1106-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a1106-107">輸入</span><span class="sxs-lookup"><span data-stu-id="a1106-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="a1106-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a1106-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a1106-109">要套用至指定資料分割的作業配對。</span><span class="sxs-lookup"><span data-stu-id="a1106-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="a1106-110">numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a1106-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a1106-111">要放入資料分割第一個部分的目標量子位數目。</span><span class="sxs-lookup"><span data-stu-id="a1106-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="a1106-112">其餘的量子位會組成資料分割的第二個部分。</span><span class="sxs-lookup"><span data-stu-id="a1106-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a1106-113">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a1106-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a1106-114">由指定的兩項作業進行分割並操作的量子位登錄。</span><span class="sxs-lookup"><span data-stu-id="a1106-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1106-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1106-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a1106-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a1106-116">See Also</span></span>

- [<span data-ttu-id="a1106-117">Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="a1106-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)