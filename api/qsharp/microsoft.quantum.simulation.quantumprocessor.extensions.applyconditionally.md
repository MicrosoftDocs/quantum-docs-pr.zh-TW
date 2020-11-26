---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229064"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="c0964-102">ApplyConditionally 操作</span><span class="sxs-lookup"><span data-stu-id="c0964-102">ApplyConditionally operation</span></span>

<span data-ttu-id="c0964-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c0964-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c0964-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c0964-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="c0964-105">輸入</span><span class="sxs-lookup"><span data-stu-id="c0964-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="c0964-106">measurementResults：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="c0964-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="c0964-107">resultsValues：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="c0964-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="c0964-108">onEqualOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0964-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="c0964-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="c0964-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="c0964-110">onNonEqualOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0964-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="c0964-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="c0964-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="c0964-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0964-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c0964-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="c0964-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c0964-114">不要</span><span class="sxs-lookup"><span data-stu-id="c0964-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="c0964-115">' U</span><span class="sxs-lookup"><span data-stu-id="c0964-115">'U</span></span>

