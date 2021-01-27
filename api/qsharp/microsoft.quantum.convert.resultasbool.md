---
uid: Microsoft.Quantum.Convert.ResultAsBool
title: ResultAsBool 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultAsBool
qsharp.summary: Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 9de7ca64992e0a4d73c1d00218b3eab4ab545a1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832551"
---
# <a name="resultasbool-function"></a><span data-ttu-id="d5cc0-102">ResultAsBool 函式</span><span class="sxs-lookup"><span data-stu-id="d5cc0-102">ResultAsBool function</span></span>

<span data-ttu-id="d5cc0-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d5cc0-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d5cc0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5cc0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5cc0-105">將型別轉換為 `Result` `Bool` 型別，其中 `One` 對應至， `true` 而且 `Zero` 會對應至 `false` 。</span><span class="sxs-lookup"><span data-stu-id="d5cc0-105">Converts a `Result` type to a `Bool` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultAsBool (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="d5cc0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d5cc0-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="d5cc0-107">輸入：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="d5cc0-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="d5cc0-108">`Result` 要轉換的。</span><span class="sxs-lookup"><span data-stu-id="d5cc0-108">`Result` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d5cc0-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d5cc0-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d5cc0-110">`Bool`，代表 `input`。</span><span class="sxs-lookup"><span data-stu-id="d5cc0-110">A `Bool` representing the `input`.</span></span>