---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 65e861914b57cf8a32f2321f881248830b72c54e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841917"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="ce24d-102">ApplyCurriedOpC 操作</span><span class="sxs-lookup"><span data-stu-id="ce24d-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="ce24d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce24d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce24d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce24d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="ce24d-105">輸入</span><span class="sxs-lookup"><span data-stu-id="ce24d-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="ce24d-106">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為 Ctl</span><span class="sxs-lookup"><span data-stu-id="ce24d-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="ce24d-107">first： t</span><span class="sxs-lookup"><span data-stu-id="ce24d-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="ce24d-108">第二個： ' U</span><span class="sxs-lookup"><span data-stu-id="ce24d-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="ce24d-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce24d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ce24d-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="ce24d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ce24d-111">不要</span><span class="sxs-lookup"><span data-stu-id="ce24d-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="ce24d-112">' U</span><span class="sxs-lookup"><span data-stu-id="ce24d-112">'U</span></span>

