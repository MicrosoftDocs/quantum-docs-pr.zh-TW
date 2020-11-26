---
uid: Microsoft.Quantum.Preparation.ApplyMultiplexStep
title: ApplyMultiplexStep 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyMultiplexStep
qsharp.summary: ''
ms.openlocfilehash: f20ae35fdb2236c2161eb74fd0fe14f222d168f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193755"
---
# <a name="applymultiplexstep-operation"></a><span data-ttu-id="fc139-102">ApplyMultiplexStep 操作</span><span class="sxs-lookup"><span data-stu-id="fc139-102">ApplyMultiplexStep operation</span></span>

<span data-ttu-id="fc139-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="fc139-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="fc139-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fc139-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyMultiplexStep (tolerance : Double, disentangling : Double[], axis : Pauli, (rngControl : Range, idxTarget : Int), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fc139-105">輸入</span><span class="sxs-lookup"><span data-stu-id="fc139-105">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="fc139-106">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fc139-106">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="disentangling--double"></a><span data-ttu-id="fc139-107">抽絲剝繭： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="fc139-107">disentangling : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>




### <a name="axis--pauli"></a><span data-ttu-id="fc139-108">軸： [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="fc139-108">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>




### <a name="rngcontrol--range"></a><span data-ttu-id="fc139-109">rngControl： [範圍](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="fc139-109">rngControl : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>




### <a name="idxtarget--int"></a><span data-ttu-id="fc139-110">idxTarget： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc139-110">idxTarget : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="register--qubit"></a><span data-ttu-id="fc139-111">register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fc139-111">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="fc139-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc139-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

