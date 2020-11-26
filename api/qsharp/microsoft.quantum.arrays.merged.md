---
uid: Microsoft.Quantum.Arrays.Merged
title: 合併函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: b3383f8a04e6fa23562aa81e5b911d06752f4fb5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220632"
---
# <a name="merged-function"></a><span data-ttu-id="b2c9b-102">合併函式</span><span class="sxs-lookup"><span data-stu-id="b2c9b-102">Merged function</span></span>

<span data-ttu-id="b2c9b-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b2c9b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b2c9b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2c9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2c9b-105">假設有兩個已排序的陣列，會傳回單一陣列，其中包含兩個專案的排序次序。</span><span class="sxs-lookup"><span data-stu-id="b2c9b-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="b2c9b-106">由定序排列在內部使用。</span><span class="sxs-lookup"><span data-stu-id="b2c9b-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b2c9b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="b2c9b-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="b2c9b-108">比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b2c9b-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="b2c9b-109">左方： t []</span><span class="sxs-lookup"><span data-stu-id="b2c9b-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="b2c9b-110">right： t []</span><span class="sxs-lookup"><span data-stu-id="b2c9b-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="b2c9b-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="b2c9b-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b2c9b-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="b2c9b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b2c9b-113">不要</span><span class="sxs-lookup"><span data-stu-id="b2c9b-113">'T</span></span>

