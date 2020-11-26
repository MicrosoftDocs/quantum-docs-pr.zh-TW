---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: f8f4f3b05d3986d94e6f1be380d6c83151d87f17
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230662"
---
# <a name="applyifone-operation"></a><span data-ttu-id="44680-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="44680-102">ApplyIfOne operation</span></span>

<span data-ttu-id="44680-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="44680-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="44680-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="44680-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="44680-105">輸入</span><span class="sxs-lookup"><span data-stu-id="44680-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="44680-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="44680-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="44680-107">onResultOneOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44680-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="44680-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="44680-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="44680-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44680-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="44680-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="44680-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="44680-111">不要</span><span class="sxs-lookup"><span data-stu-id="44680-111">'T</span></span>

