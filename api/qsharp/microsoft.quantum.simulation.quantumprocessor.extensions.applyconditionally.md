---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 67a4dcba5c193222c06ab429813adf12d7bbedfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847890"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="c716e-102">ApplyConditionally 操作</span><span class="sxs-lookup"><span data-stu-id="c716e-102">ApplyConditionally operation</span></span>

<span data-ttu-id="c716e-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c716e-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c716e-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c716e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="c716e-105">輸入</span><span class="sxs-lookup"><span data-stu-id="c716e-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="c716e-106">measurementResults：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="c716e-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="c716e-107">resultsValues：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="c716e-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="c716e-108">onEqualOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c716e-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="c716e-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="c716e-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="c716e-110">onNonEqualOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c716e-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="c716e-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="c716e-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="c716e-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c716e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c716e-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="c716e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c716e-114">不要</span><span class="sxs-lookup"><span data-stu-id="c716e-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="c716e-115">' U</span><span class="sxs-lookup"><span data-stu-id="c716e-115">'U</span></span>

