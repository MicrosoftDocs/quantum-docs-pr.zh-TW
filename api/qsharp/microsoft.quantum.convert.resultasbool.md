---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 34fca15faf79f706b398e3fdfc537ea91b28da86
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698258"
---
# <a name="resultasbool-function"></a><span data-ttu-id="2e79b-102">ResultAsBool 函式</span><span class="sxs-lookup"><span data-stu-id="2e79b-102">ResultAsBool function</span></span>

<span data-ttu-id="2e79b-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="2e79b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="2e79b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e79b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e79b-105">將型別轉換為 `Result` `Bool` 型別，其中 `One` 對應至， `true` 而且 `Zero` 會對應至 `false` 。</span><span class="sxs-lookup"><span data-stu-id="2e79b-105">Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="2e79b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2e79b-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="2e79b-107">輸入： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="2e79b-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="2e79b-108">`Result` 要轉換的。</span><span class="sxs-lookup"><span data-stu-id="2e79b-108">`Result` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2e79b-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e79b-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2e79b-110">`Bool`，代表 `input`。</span><span class="sxs-lookup"><span data-stu-id="2e79b-110">A `Bool` representing the `input`.</span></span>