---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194146"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="00d4d-102">SetToBasisState 操作</span><span class="sxs-lookup"><span data-stu-id="00d4d-102">SetToBasisState operation</span></span>

<span data-ttu-id="00d4d-103">命名空間： [Microsoft 量子. 度量](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="00d4d-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="00d4d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="00d4d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="00d4d-105">藉由測量量子位並視需要套用位翻轉，將量子位設定為指定的計算基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="00d4d-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="00d4d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="00d4d-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="00d4d-107">需要：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="00d4d-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="00d4d-108">應設定量子位的基礎狀態。</span><span class="sxs-lookup"><span data-stu-id="00d4d-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="00d4d-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="00d4d-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="00d4d-110">要設定其狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="00d4d-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="00d4d-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="00d4d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="00d4d-112">備註</span><span class="sxs-lookup"><span data-stu-id="00d4d-112">Remarks</span></span>

<span data-ttu-id="00d4d-113">這項作業的非變異， `M(q)` 會在之後立即呼叫 `SetToBasisState(result, q)` `result` 。</span><span class="sxs-lookup"><span data-stu-id="00d4d-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>