---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: 9e391b61aa4d22ad02bf657a866f959d35b6628f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192667"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="7e9f1-102">ApplyIfElseR 操作</span><span class="sxs-lookup"><span data-stu-id="7e9f1-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="7e9f1-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7e9f1-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7e9f1-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7e9f1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="7e9f1-105">輸入</span><span class="sxs-lookup"><span data-stu-id="7e9f1-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="7e9f1-106">measurementResult：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7e9f1-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="7e9f1-107">onResultZeroOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e9f1-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="7e9f1-108">zeroArg： t</span><span class="sxs-lookup"><span data-stu-id="7e9f1-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="7e9f1-109">onResultOneOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e9f1-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="7e9f1-110">oneArg： ' U</span><span class="sxs-lookup"><span data-stu-id="7e9f1-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7e9f1-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e9f1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7e9f1-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="7e9f1-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7e9f1-113">不要</span><span class="sxs-lookup"><span data-stu-id="7e9f1-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="7e9f1-114">' U</span><span class="sxs-lookup"><span data-stu-id="7e9f1-114">'U</span></span>

