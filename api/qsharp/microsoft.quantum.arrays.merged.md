---
uid: Microsoft.Quantum.Arrays.Merged
title: 合併函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699445"
---
# <a name="merged-function"></a><span data-ttu-id="db47e-102">合併函式</span><span class="sxs-lookup"><span data-stu-id="db47e-102">Merged function</span></span>

<span data-ttu-id="db47e-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="db47e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="db47e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="db47e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="db47e-105">假設有兩個已排序的陣列，會傳回單一陣列，其中包含兩個專案的排序次序。</span><span class="sxs-lookup"><span data-stu-id="db47e-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="db47e-106">由定序排列在內部使用。</span><span class="sxs-lookup"><span data-stu-id="db47e-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="db47e-107">輸入</span><span class="sxs-lookup"><span data-stu-id="db47e-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="db47e-108">比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="db47e-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="db47e-109">左方： t []</span><span class="sxs-lookup"><span data-stu-id="db47e-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="db47e-110">right： t []</span><span class="sxs-lookup"><span data-stu-id="db47e-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="db47e-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="db47e-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="db47e-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="db47e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db47e-113">不要</span><span class="sxs-lookup"><span data-stu-id="db47e-113">'T</span></span>

