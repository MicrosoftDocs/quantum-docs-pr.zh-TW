---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: ApplyIfOneA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: 63ce44300f6e50cb91294b62611275e3e8942655
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855603"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="fdd8d-102">ApplyIfOneA 操作</span><span class="sxs-lookup"><span data-stu-id="fdd8d-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="fdd8d-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="fdd8d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="fdd8d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fdd8d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="fdd8d-105">輸入</span><span class="sxs-lookup"><span data-stu-id="fdd8d-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="fdd8d-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="fdd8d-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj"></a><span data-ttu-id="fdd8d-107">onResultOneOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="fdd8d-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="fdd8d-108">oneArg： t</span><span class="sxs-lookup"><span data-stu-id="fdd8d-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="fdd8d-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fdd8d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fdd8d-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="fdd8d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fdd8d-111">不要</span><span class="sxs-lookup"><span data-stu-id="fdd8d-111">'T</span></span>

