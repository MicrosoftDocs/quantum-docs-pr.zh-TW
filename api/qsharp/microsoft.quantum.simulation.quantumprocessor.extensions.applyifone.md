---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: fd5ee65615e4910d60db83cb8ec4201cfff9035d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855600"
---
# <a name="applyifone-operation"></a><span data-ttu-id="661db-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="661db-102">ApplyIfOne operation</span></span>

<span data-ttu-id="661db-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="661db-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="661db-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="661db-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="661db-105">輸入</span><span class="sxs-lookup"><span data-stu-id="661db-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="661db-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="661db-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="661db-107">onResultOneOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="661db-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="661db-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="661db-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="661db-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="661db-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="661db-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="661db-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="661db-111">不要</span><span class="sxs-lookup"><span data-stu-id="661db-111">'T</span></span>

