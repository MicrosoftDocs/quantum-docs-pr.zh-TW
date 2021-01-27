---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840897"
---
# <a name="composedoutput-function"></a><span data-ttu-id="4f569-102">ComposedOutput 函式</span><span class="sxs-lookup"><span data-stu-id="4f569-102">ComposedOutput function</span></span>

<span data-ttu-id="4f569-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4f569-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4f569-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f569-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f569-105">`inner`傳回指定輸入之和的組合輸出 `outer` 。</span><span class="sxs-lookup"><span data-stu-id="4f569-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="4f569-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4f569-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="4f569-107">外部： ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="4f569-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="4f569-108">內部： t-> ' U</span><span class="sxs-lookup"><span data-stu-id="4f569-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="4f569-109">目標： t</span><span class="sxs-lookup"><span data-stu-id="4f569-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="4f569-110">輸出： ' V</span><span class="sxs-lookup"><span data-stu-id="4f569-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4f569-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="4f569-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4f569-112">不要</span><span class="sxs-lookup"><span data-stu-id="4f569-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="4f569-113">' U</span><span class="sxs-lookup"><span data-stu-id="4f569-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="4f569-114">' V</span><span class="sxs-lookup"><span data-stu-id="4f569-114">'V</span></span>

