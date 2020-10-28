---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: ApplyIfOneC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: 8456201d4ed137f3d84013f3b5170b52b27e66c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701114"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="f2561-102">ApplyIfOneC 操作</span><span class="sxs-lookup"><span data-stu-id="f2561-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="f2561-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="f2561-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f2561-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2561-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="f2561-105">輸入</span><span class="sxs-lookup"><span data-stu-id="f2561-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="f2561-106">measurementResult： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="f2561-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-ctl"></a><span data-ttu-id="f2561-107">onResultOneOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="f2561-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="f2561-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="f2561-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="f2561-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2561-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f2561-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="f2561-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f2561-111">不要</span><span class="sxs-lookup"><span data-stu-id="f2561-111">'T</span></span>

