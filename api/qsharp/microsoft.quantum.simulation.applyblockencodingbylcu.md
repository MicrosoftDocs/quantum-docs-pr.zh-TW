---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852818"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="9f663-102">ApplyBlockEncodingByLCU 操作</span><span class="sxs-lookup"><span data-stu-id="9f663-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="9f663-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9f663-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9f663-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f663-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f663-105">`BlockEncodingByLCU` 的實作。</span><span class="sxs-lookup"><span data-stu-id="9f663-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9f663-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9f663-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="9f663-107">statePreparation： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9f663-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="9f663-108">選取器： ( t，) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9f663-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="9f663-109">輔助： t</span><span class="sxs-lookup"><span data-stu-id="9f663-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="9f663-110">system：</span><span class="sxs-lookup"><span data-stu-id="9f663-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="9f663-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f663-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9f663-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="9f663-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f663-113">不要</span><span class="sxs-lookup"><span data-stu-id="9f663-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="9f663-114">者</span><span class="sxs-lookup"><span data-stu-id="9f663-114">'S</span></span>

