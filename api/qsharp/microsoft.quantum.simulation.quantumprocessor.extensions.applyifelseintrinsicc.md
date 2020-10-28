---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicC
title: ApplyIfElseIntrinsicC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 178d4b704d84090f1f8592b857c3da659e5c50bb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700942"
---
# <a name="applyifelseintrinsicc-operation"></a><span data-ttu-id="ab8a2-102">ApplyIfElseIntrinsicC 操作</span><span class="sxs-lookup"><span data-stu-id="ab8a2-102">ApplyIfElseIntrinsicC operation</span></span>

<span data-ttu-id="ab8a2-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="ab8a2-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="ab8a2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab8a2-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseIntrinsicC (measurementResult : Result, onResultZeroOp : (Unit => Unit is Ctl), onResultOneOp : (Unit => Unit is Ctl)) : Unit
```


## <a name="input"></a><span data-ttu-id="ab8a2-105">輸入</span><span class="sxs-lookup"><span data-stu-id="ab8a2-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="ab8a2-106">measurementResult： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="ab8a2-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit-ctl"></a><span data-ttu-id="ab8a2-107">onResultZeroOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="ab8a2-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onresultoneop--unit--unit-ctl"></a><span data-ttu-id="ab8a2-108">onResultOneOp： [單位](xref:microsoft.quantum.lang-ref.unit) => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="ab8a2-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="ab8a2-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab8a2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

