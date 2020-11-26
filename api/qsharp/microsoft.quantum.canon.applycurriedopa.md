---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: db3f63cbe2ee5ef048c7e378864d68696f55331f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218949"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="cf74f-102">ApplyCurriedOpA 操作</span><span class="sxs-lookup"><span data-stu-id="cf74f-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="cf74f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cf74f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cf74f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cf74f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="cf74f-105">輸入</span><span class="sxs-lookup"><span data-stu-id="cf74f-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="cf74f-106">curriedOp： t-> ' U => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="cf74f-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="cf74f-107">first： t</span><span class="sxs-lookup"><span data-stu-id="cf74f-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="cf74f-108">第二個： ' U</span><span class="sxs-lookup"><span data-stu-id="cf74f-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="cf74f-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf74f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cf74f-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="cf74f-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cf74f-111">不要</span><span class="sxs-lookup"><span data-stu-id="cf74f-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="cf74f-112">' U</span><span class="sxs-lookup"><span data-stu-id="cf74f-112">'U</span></span>

