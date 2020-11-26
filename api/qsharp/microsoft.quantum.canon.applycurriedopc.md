---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: faca9b3f6d9a132b591a532c9e2ce54af1f0b182
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218932"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="78289-102">ApplyCurriedOpC 操作</span><span class="sxs-lookup"><span data-stu-id="78289-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="78289-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="78289-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="78289-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78289-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="78289-105">輸入</span><span class="sxs-lookup"><span data-stu-id="78289-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="78289-106">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為 Ctl</span><span class="sxs-lookup"><span data-stu-id="78289-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="78289-107">first： t</span><span class="sxs-lookup"><span data-stu-id="78289-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="78289-108">第二個： ' U</span><span class="sxs-lookup"><span data-stu-id="78289-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="78289-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78289-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="78289-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="78289-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="78289-111">不要</span><span class="sxs-lookup"><span data-stu-id="78289-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="78289-112">' U</span><span class="sxs-lookup"><span data-stu-id="78289-112">'U</span></span>

