---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 50a2bdb4a73ef9d67d3f5532493c142bb7f753cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698330"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="04948-102">BoolArrayAsResultArray 函式</span><span class="sxs-lookup"><span data-stu-id="04948-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="04948-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="04948-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="04948-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="04948-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="04948-105">將型別轉換為 `Bool[]` `Result[]` 型別，其中 `true` 對應至， `One` 而且 `false` 會對應至 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="04948-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="04948-106">輸入</span><span class="sxs-lookup"><span data-stu-id="04948-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="04948-107">輸入： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="04948-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="04948-108">`Bool[]` 要轉換的。</span><span class="sxs-lookup"><span data-stu-id="04948-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="04948-109">輸出： __無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="04948-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="04948-110">`Result[]`，代表 `input`。</span><span class="sxs-lookup"><span data-stu-id="04948-110">A `Result[]` representing the `input`.</span></span>