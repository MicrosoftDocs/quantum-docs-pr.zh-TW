---
uid: Microsoft.Quantum.Arrays.Merged
title: 合併函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845617"
---
# <a name="merged-function"></a><span data-ttu-id="73d13-102">合併函式</span><span class="sxs-lookup"><span data-stu-id="73d13-102">Merged function</span></span>

<span data-ttu-id="73d13-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="73d13-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="73d13-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73d13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73d13-105">假設有兩個已排序的陣列，會傳回單一陣列，其中包含兩個專案的排序次序。</span><span class="sxs-lookup"><span data-stu-id="73d13-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="73d13-106">由定序排列在內部使用。</span><span class="sxs-lookup"><span data-stu-id="73d13-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="73d13-107">輸入</span><span class="sxs-lookup"><span data-stu-id="73d13-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="73d13-108">比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="73d13-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="73d13-109">左方： t []</span><span class="sxs-lookup"><span data-stu-id="73d13-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="73d13-110">right： t []</span><span class="sxs-lookup"><span data-stu-id="73d13-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="73d13-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="73d13-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="73d13-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="73d13-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="73d13-113">不要</span><span class="sxs-lookup"><span data-stu-id="73d13-113">'T</span></span>

