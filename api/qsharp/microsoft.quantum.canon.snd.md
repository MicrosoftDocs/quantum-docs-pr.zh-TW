---
uid: Microsoft.Quantum.Canon.Snd
title: Operators.snd 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852163"
---
# <a name="snd-function"></a><span data-ttu-id="f7128-102">Operators.snd 函式</span><span class="sxs-lookup"><span data-stu-id="f7128-102">Snd function</span></span>

<span data-ttu-id="f7128-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7128-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7128-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7128-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7128-105">如果指定了配對，會傳回它的第二個元素。</span><span class="sxs-lookup"><span data-stu-id="f7128-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="f7128-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f7128-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="f7128-107">配對： ( t，' U) </span><span class="sxs-lookup"><span data-stu-id="f7128-107">pair : ('T,'U)</span></span>

<span data-ttu-id="f7128-108">具有兩個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="f7128-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="f7128-109">輸出： ' U</span><span class="sxs-lookup"><span data-stu-id="f7128-109">Output : 'U</span></span>

<span data-ttu-id="f7128-110">的第二個元素 `pair` 。</span><span class="sxs-lookup"><span data-stu-id="f7128-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f7128-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="f7128-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7128-112">不要</span><span class="sxs-lookup"><span data-stu-id="f7128-112">'T</span></span>

<span data-ttu-id="f7128-113">配對第一個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="f7128-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="f7128-114">' U</span><span class="sxs-lookup"><span data-stu-id="f7128-114">'U</span></span>

<span data-ttu-id="f7128-115">配對第二個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="f7128-115">The type of the pair's second member.</span></span>