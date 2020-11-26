---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: ApplyIfZeroC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 9a73ea9ec607bec89c996c096b235a72185b453d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230832"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="71a8d-102">ApplyIfZeroC 操作</span><span class="sxs-lookup"><span data-stu-id="71a8d-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="71a8d-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="71a8d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="71a8d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="71a8d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="71a8d-105">輸入</span><span class="sxs-lookup"><span data-stu-id="71a8d-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="71a8d-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="71a8d-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="71a8d-107">onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  是 Ctl</span><span class="sxs-lookup"><span data-stu-id="71a8d-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="71a8d-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="71a8d-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="71a8d-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71a8d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="71a8d-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="71a8d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="71a8d-111">不要</span><span class="sxs-lookup"><span data-stu-id="71a8d-111">'T</span></span>

