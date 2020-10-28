---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699003"
---
# <a name="isresultone-function"></a><span data-ttu-id="41158-102">IsResultOne 函式</span><span class="sxs-lookup"><span data-stu-id="41158-102">IsResultOne function</span></span>

<span data-ttu-id="41158-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41158-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41158-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41158-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41158-105">測試給定的結果值是否等於 `One` 。</span><span class="sxs-lookup"><span data-stu-id="41158-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="41158-106">輸入</span><span class="sxs-lookup"><span data-stu-id="41158-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="41158-107">輸入： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="41158-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="41158-108">`Result` 要測試的值。</span><span class="sxs-lookup"><span data-stu-id="41158-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="41158-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="41158-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="41158-110">`true`如果 `input` 等於，則會傳回 `One` 。</span><span class="sxs-lookup"><span data-stu-id="41158-110">Returns `true` if `input` is equal to `One`.</span></span>