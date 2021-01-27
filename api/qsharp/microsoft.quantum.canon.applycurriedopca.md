---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: ApplyCurriedOpCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: acff5669c8d5d392a0032eaa49d279bff20a91f4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845061"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="885ba-102">ApplyCurriedOpCA 操作</span><span class="sxs-lookup"><span data-stu-id="885ba-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="885ba-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="885ba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="885ba-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="885ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="885ba-105">輸入</span><span class="sxs-lookup"><span data-stu-id="885ba-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="885ba-106">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="885ba-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="885ba-107">first： t</span><span class="sxs-lookup"><span data-stu-id="885ba-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="885ba-108">第二個： ' U</span><span class="sxs-lookup"><span data-stu-id="885ba-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="885ba-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="885ba-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="885ba-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="885ba-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="885ba-111">不要</span><span class="sxs-lookup"><span data-stu-id="885ba-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="885ba-112">' U</span><span class="sxs-lookup"><span data-stu-id="885ba-112">'U</span></span>

