---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0ed5c81cb80458e2f56ba2fcaac03eb92a534bea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834178"
---
# <a name="boolasresult-function"></a><span data-ttu-id="da235-102">BoolAsResult 函式</span><span class="sxs-lookup"><span data-stu-id="da235-102">BoolAsResult function</span></span>

<span data-ttu-id="da235-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="da235-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="da235-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da235-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da235-105">將型別轉換為 `Bool` `Result` 型別，其中 `true` 對應至， `One` 而且 `false` 會對應至 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="da235-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="da235-106">輸入</span><span class="sxs-lookup"><span data-stu-id="da235-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="da235-107">輸入： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="da235-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="da235-108">`Bool` 要轉換的。</span><span class="sxs-lookup"><span data-stu-id="da235-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="da235-109">輸出：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="da235-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="da235-110">`Result`，代表 `input`。</span><span class="sxs-lookup"><span data-stu-id="da235-110">A `Result` representing the `input`.</span></span>