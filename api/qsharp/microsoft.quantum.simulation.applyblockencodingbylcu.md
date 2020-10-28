---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700182"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="fd3f2-102">ApplyBlockEncodingByLCU 操作</span><span class="sxs-lookup"><span data-stu-id="fd3f2-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="fd3f2-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="fd3f2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="fd3f2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fd3f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fd3f2-105">`BlockEncodingByLCU` 的實作。</span><span class="sxs-lookup"><span data-stu-id="fd3f2-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a><span data-ttu-id="fd3f2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="fd3f2-106">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="fd3f2-107">statePreparation： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fd3f2-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="fd3f2-108">選取器： ( t，) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fd3f2-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="fd3f2-109">輔助： t</span><span class="sxs-lookup"><span data-stu-id="fd3f2-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="fd3f2-110">system：</span><span class="sxs-lookup"><span data-stu-id="fd3f2-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="fd3f2-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd3f2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fd3f2-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="fd3f2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fd3f2-113">不要</span><span class="sxs-lookup"><span data-stu-id="fd3f2-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="fd3f2-114">者</span><span class="sxs-lookup"><span data-stu-id="fd3f2-114">'S</span></span>

