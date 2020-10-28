---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: ApplyIfZeroA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 124c5bbabc9e22804734ddbde955312db9655187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701203"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="705fe-102">ApplyIfZeroA 操作</span><span class="sxs-lookup"><span data-stu-id="705fe-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="705fe-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="705fe-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="705fe-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="705fe-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="705fe-105">輸入</span><span class="sxs-lookup"><span data-stu-id="705fe-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="705fe-106">measurementResult： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="705fe-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj"></a><span data-ttu-id="705fe-107">onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="705fe-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="705fe-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="705fe-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="705fe-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="705fe-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="705fe-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="705fe-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="705fe-111">不要</span><span class="sxs-lookup"><span data-stu-id="705fe-111">'T</span></span>

