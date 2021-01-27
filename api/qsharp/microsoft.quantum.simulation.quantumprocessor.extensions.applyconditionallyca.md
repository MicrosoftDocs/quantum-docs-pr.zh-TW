---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: ApplyConditionallyCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: ce82ae10341d3be5f6e0e025631e5dd91a33e622
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847847"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="15488-102">ApplyConditionallyCA 操作</span><span class="sxs-lookup"><span data-stu-id="15488-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="15488-103">命名空間： [QuantumProcessor 副檔名](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="15488-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="15488-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="15488-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="15488-105">輸入</span><span class="sxs-lookup"><span data-stu-id="15488-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="15488-106">measurementResults：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="15488-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="15488-107">resultsValues：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="15488-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj--ctl"></a><span data-ttu-id="15488-108">onEqualOp： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="15488-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="15488-109">equalArg： t</span><span class="sxs-lookup"><span data-stu-id="15488-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj--ctl"></a><span data-ttu-id="15488-110">onNonEqualOp： ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="15488-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="15488-111">nonEqualArg： ' U</span><span class="sxs-lookup"><span data-stu-id="15488-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="15488-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15488-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="15488-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="15488-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15488-114">不要</span><span class="sxs-lookup"><span data-stu-id="15488-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="15488-115">' U</span><span class="sxs-lookup"><span data-stu-id="15488-115">'U</span></span>

