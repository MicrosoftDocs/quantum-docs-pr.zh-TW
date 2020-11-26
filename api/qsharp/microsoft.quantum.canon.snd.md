---
uid: Microsoft.Quantum.Canon.Snd
title: Operators.snd 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205315"
---
# <a name="snd-function"></a><span data-ttu-id="896cb-102">Operators.snd 函式</span><span class="sxs-lookup"><span data-stu-id="896cb-102">Snd function</span></span>

<span data-ttu-id="896cb-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="896cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="896cb-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="896cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="896cb-105">如果指定了配對，會傳回它的第二個元素。</span><span class="sxs-lookup"><span data-stu-id="896cb-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="896cb-106">輸入</span><span class="sxs-lookup"><span data-stu-id="896cb-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="896cb-107">配對： ( t，' U) </span><span class="sxs-lookup"><span data-stu-id="896cb-107">pair : ('T,'U)</span></span>

<span data-ttu-id="896cb-108">具有兩個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="896cb-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="896cb-109">輸出： ' U</span><span class="sxs-lookup"><span data-stu-id="896cb-109">Output : 'U</span></span>

<span data-ttu-id="896cb-110">的第二個元素 `pair` 。</span><span class="sxs-lookup"><span data-stu-id="896cb-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="896cb-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="896cb-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="896cb-112">不要</span><span class="sxs-lookup"><span data-stu-id="896cb-112">'T</span></span>

<span data-ttu-id="896cb-113">配對第一個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="896cb-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="896cb-114">' U</span><span class="sxs-lookup"><span data-stu-id="896cb-114">'U</span></span>

<span data-ttu-id="896cb-115">配對第二個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="896cb-115">The type of the pair's second member.</span></span>