---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699065"
---
# <a name="composedoutput-function"></a><span data-ttu-id="533c2-102">ComposedOutput 函式</span><span class="sxs-lookup"><span data-stu-id="533c2-102">ComposedOutput function</span></span>

<span data-ttu-id="533c2-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="533c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="533c2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="533c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="533c2-105">`inner`傳回指定輸入之和的組合輸出 `outer` 。</span><span class="sxs-lookup"><span data-stu-id="533c2-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="533c2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="533c2-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="533c2-107">外部： ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="533c2-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="533c2-108">內部： t-> ' U</span><span class="sxs-lookup"><span data-stu-id="533c2-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="533c2-109">目標： t</span><span class="sxs-lookup"><span data-stu-id="533c2-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="533c2-110">輸出： ' V</span><span class="sxs-lookup"><span data-stu-id="533c2-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="533c2-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="533c2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="533c2-112">不要</span><span class="sxs-lookup"><span data-stu-id="533c2-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="533c2-113">' U</span><span class="sxs-lookup"><span data-stu-id="533c2-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="533c2-114">' V</span><span class="sxs-lookup"><span data-stu-id="533c2-114">'V</span></span>

