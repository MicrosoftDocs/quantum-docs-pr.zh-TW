---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698327"
---
# <a name="boolasresult-function"></a><span data-ttu-id="0f909-102">BoolAsResult 函式</span><span class="sxs-lookup"><span data-stu-id="0f909-102">BoolAsResult function</span></span>

<span data-ttu-id="0f909-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="0f909-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="0f909-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f909-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f909-105">將型別轉換為 `Bool` `Result` 型別，其中 `true` 對應至， `One` 而且 `false` 會對應至 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="0f909-105">Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a><span data-ttu-id="0f909-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0f909-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="0f909-107">輸入： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0f909-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0f909-108">`Bool` 要轉換的。</span><span class="sxs-lookup"><span data-stu-id="0f909-108">`Bool` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="0f909-109">輸出： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="0f909-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="0f909-110">`Result`，代表 `input`。</span><span class="sxs-lookup"><span data-stu-id="0f909-110">A `Result` representing the `input`.</span></span>