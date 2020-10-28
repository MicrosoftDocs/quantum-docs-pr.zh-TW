---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700910"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="e90fd-102">SetToBasisState 操作</span><span class="sxs-lookup"><span data-stu-id="e90fd-102">SetToBasisState operation</span></span>

<span data-ttu-id="e90fd-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e90fd-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e90fd-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e90fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e90fd-105">藉由測量量子位並視需要套用位翻轉，將量子位設定為指定的計算基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="e90fd-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e90fd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e90fd-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="e90fd-107">需要： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="e90fd-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="e90fd-108">應設定量子位的基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="e90fd-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e90fd-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e90fd-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e90fd-110">要設定其狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="e90fd-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e90fd-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e90fd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e90fd-112">備註</span><span class="sxs-lookup"><span data-stu-id="e90fd-112">Remarks</span></span>

<span data-ttu-id="e90fd-113">這項作業的非變異， `M(q)` 會在之後立即呼叫 `SetToBasisState(result, q)` `result` 。</span><span class="sxs-lookup"><span data-stu-id="e90fd-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>