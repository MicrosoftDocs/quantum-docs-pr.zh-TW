---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 2b0f86efe79654e1f886f0ccd0287e07225cbf83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699332"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="872e8-102">ApplyCurriedOpA 操作</span><span class="sxs-lookup"><span data-stu-id="872e8-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="872e8-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="872e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="872e8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="872e8-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="872e8-105">輸入</span><span class="sxs-lookup"><span data-stu-id="872e8-105">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="872e8-106">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="872e8-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="872e8-107">first： t</span><span class="sxs-lookup"><span data-stu-id="872e8-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="872e8-108">第二個： ' U</span><span class="sxs-lookup"><span data-stu-id="872e8-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="872e8-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="872e8-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="872e8-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="872e8-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="872e8-111">不要</span><span class="sxs-lookup"><span data-stu-id="872e8-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="872e8-112">' U</span><span class="sxs-lookup"><span data-stu-id="872e8-112">'U</span></span>

