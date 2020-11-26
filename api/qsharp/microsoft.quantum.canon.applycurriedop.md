---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: ab652159fa64a95401d07998ed4aaae5c4dbb92e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219017"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="8ec91-102">ApplyCurriedOp 操作</span><span class="sxs-lookup"><span data-stu-id="8ec91-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="8ec91-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ec91-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ec91-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ec91-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="8ec91-105">輸入</span><span class="sxs-lookup"><span data-stu-id="8ec91-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="8ec91-106">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ec91-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="8ec91-107">first： t</span><span class="sxs-lookup"><span data-stu-id="8ec91-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="8ec91-108">第二個： ' U</span><span class="sxs-lookup"><span data-stu-id="8ec91-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="8ec91-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ec91-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ec91-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="8ec91-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ec91-111">不要</span><span class="sxs-lookup"><span data-stu-id="8ec91-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="8ec91-112">' U</span><span class="sxs-lookup"><span data-stu-id="8ec91-112">'U</span></span>

