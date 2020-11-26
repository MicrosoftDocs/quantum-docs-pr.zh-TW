---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneC
title: ApplyIfOneC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneC
qsharp.summary: ''
ms.openlocfilehash: d7c4e39ba26befeabad612e888da4abd00efaeb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230951"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="29380-102">ApplyIfOneC 操作</span><span class="sxs-lookup"><span data-stu-id="29380-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="29380-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="29380-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="29380-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="29380-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneC<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl), oneArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="29380-105">輸入</span><span class="sxs-lookup"><span data-stu-id="29380-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="29380-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="29380-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-ctl"></a><span data-ttu-id="29380-107">onResultOneOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="29380-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="29380-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="29380-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="29380-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29380-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="29380-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="29380-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29380-111">不要</span><span class="sxs-lookup"><span data-stu-id="29380-111">'T</span></span>

