---
uid: Microsoft.Quantum.Canon.Snd
title: Operators.snd 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698859"
---
# <a name="snd-function"></a><span data-ttu-id="47172-102">Operators.snd 函式</span><span class="sxs-lookup"><span data-stu-id="47172-102">Snd function</span></span>

<span data-ttu-id="47172-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47172-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47172-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47172-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47172-105">如果指定了配對，會傳回它的第二個元素。</span><span class="sxs-lookup"><span data-stu-id="47172-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="47172-106">輸入</span><span class="sxs-lookup"><span data-stu-id="47172-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="47172-107">配對： ( t，' U) </span><span class="sxs-lookup"><span data-stu-id="47172-107">pair : ('T,'U)</span></span>

<span data-ttu-id="47172-108">具有兩個元素的元組。</span><span class="sxs-lookup"><span data-stu-id="47172-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="47172-109">輸出： ' U</span><span class="sxs-lookup"><span data-stu-id="47172-109">Output : 'U</span></span>

<span data-ttu-id="47172-110">的第二個元素 `pair` 。</span><span class="sxs-lookup"><span data-stu-id="47172-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="47172-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="47172-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47172-112">不要</span><span class="sxs-lookup"><span data-stu-id="47172-112">'T</span></span>

<span data-ttu-id="47172-113">配對第一個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="47172-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="47172-114">' U</span><span class="sxs-lookup"><span data-stu-id="47172-114">'U</span></span>

<span data-ttu-id="47172-115">配對第二個成員的類型。</span><span class="sxs-lookup"><span data-stu-id="47172-115">The type of the pair's second member.</span></span>