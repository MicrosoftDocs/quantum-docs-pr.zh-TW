---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 0356fe9c98306ee3e1857f4af311aef9b3789a7d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698262"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="6f051-102">ResultArrayAsBoolArray 函式</span><span class="sxs-lookup"><span data-stu-id="6f051-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="6f051-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="6f051-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="6f051-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f051-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f051-105">將型別轉換為 `Result[]` `Bool[]` 型別，其中 `One` 對應至， `true` 而且 `Zero` 會對應至 `false` 。</span><span class="sxs-lookup"><span data-stu-id="6f051-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="6f051-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6f051-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="6f051-107">輸入： __無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="6f051-107">input : __invalid<Result>__ []</span></span>

<span data-ttu-id="6f051-108">`Result[]` 要轉換的。</span><span class="sxs-lookup"><span data-stu-id="6f051-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6f051-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6f051-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6f051-110">`Bool[]`，代表 `input`。</span><span class="sxs-lookup"><span data-stu-id="6f051-110">A `Bool[]` representing the `input`.</span></span>