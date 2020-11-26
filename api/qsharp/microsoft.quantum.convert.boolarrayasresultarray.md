---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224457"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="b946e-102">BoolArrayAsResultArray 函式</span><span class="sxs-lookup"><span data-stu-id="b946e-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="b946e-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="b946e-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="b946e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b946e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b946e-105">將型別轉換為 `Bool[]` `Result[]` 型別，其中 `true` 對應至， `One` 而且 `false` 會對應至 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="b946e-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="b946e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b946e-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="b946e-107">輸入： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b946e-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b946e-108">`Bool[]` 要轉換的。</span><span class="sxs-lookup"><span data-stu-id="b946e-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="b946e-109">輸出：__無效 <Result>__ 的 []</span><span class="sxs-lookup"><span data-stu-id="b946e-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="b946e-110">`Result[]`，代表 `input`。</span><span class="sxs-lookup"><span data-stu-id="b946e-110">A `Result[]` representing the `input`.</span></span>