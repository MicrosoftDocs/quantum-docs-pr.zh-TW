---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207457"
---
# <a name="composedoutput-function"></a><span data-ttu-id="738a4-102">ComposedOutput 函式</span><span class="sxs-lookup"><span data-stu-id="738a4-102">ComposedOutput function</span></span>

<span data-ttu-id="738a4-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="738a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="738a4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="738a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="738a4-105">`inner`傳回指定輸入之和的組合輸出 `outer` 。</span><span class="sxs-lookup"><span data-stu-id="738a4-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="738a4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="738a4-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="738a4-107">外部： ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="738a4-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="738a4-108">內部： t-> ' U</span><span class="sxs-lookup"><span data-stu-id="738a4-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="738a4-109">目標： t</span><span class="sxs-lookup"><span data-stu-id="738a4-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="738a4-110">輸出： ' V</span><span class="sxs-lookup"><span data-stu-id="738a4-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="738a4-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="738a4-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="738a4-112">不要</span><span class="sxs-lookup"><span data-stu-id="738a4-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="738a4-113">' U</span><span class="sxs-lookup"><span data-stu-id="738a4-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="738a4-114">' V</span><span class="sxs-lookup"><span data-stu-id="738a4-114">'V</span></span>

