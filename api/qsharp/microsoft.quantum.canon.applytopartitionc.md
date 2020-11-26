---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: ApplyToPartitionC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 22af7a3704f88a4d1973149e7387ebb683468540
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208260"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="f3e29-102">ApplyToPartitionC 操作</span><span class="sxs-lookup"><span data-stu-id="f3e29-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="f3e29-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f3e29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f3e29-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3e29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3e29-105">將一組作業套用至註冊的指定分割區分成兩個部分。</span><span class="sxs-lookup"><span data-stu-id="f3e29-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="f3e29-106">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="f3e29-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f3e29-107">輸入</span><span class="sxs-lookup"><span data-stu-id="f3e29-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="f3e29-108">op： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)  為 Ctl</span><span class="sxs-lookup"><span data-stu-id="f3e29-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f3e29-109">要套用至指定資料分割的作業配對。</span><span class="sxs-lookup"><span data-stu-id="f3e29-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="f3e29-110">numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f3e29-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f3e29-111">要放入資料分割第一個部分的目標量子位數目。</span><span class="sxs-lookup"><span data-stu-id="f3e29-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="f3e29-112">其餘的量子位會組成資料分割的第二個部分。</span><span class="sxs-lookup"><span data-stu-id="f3e29-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f3e29-113">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f3e29-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f3e29-114">由指定的兩項作業進行分割並操作的量子位登錄。</span><span class="sxs-lookup"><span data-stu-id="f3e29-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3e29-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3e29-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f3e29-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f3e29-116">See Also</span></span>

- [<span data-ttu-id="f3e29-117">Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="f3e29-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)