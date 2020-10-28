---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 1a00fe91889e3100e4d3272d258877b4ec88618f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699330"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="ee526-102">ApplyCurriedOpC 操作</span><span class="sxs-lookup"><span data-stu-id="ee526-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="ee526-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee526-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee526-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee526-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="ee526-105">輸入</span><span class="sxs-lookup"><span data-stu-id="ee526-105">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="ee526-106">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="ee526-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="ee526-107">first： t</span><span class="sxs-lookup"><span data-stu-id="ee526-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="ee526-108">第二個： ' U</span><span class="sxs-lookup"><span data-stu-id="ee526-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ee526-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee526-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee526-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="ee526-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee526-111">不要</span><span class="sxs-lookup"><span data-stu-id="ee526-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="ee526-112">' U</span><span class="sxs-lookup"><span data-stu-id="ee526-112">'U</span></span>

