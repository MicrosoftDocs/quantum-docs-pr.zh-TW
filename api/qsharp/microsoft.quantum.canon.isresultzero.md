---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699000"
---
# <a name="isresultzero-function"></a><span data-ttu-id="c5cb6-102">IsResultZero 函式</span><span class="sxs-lookup"><span data-stu-id="c5cb6-102">IsResultZero function</span></span>

<span data-ttu-id="c5cb6-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c5cb6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c5cb6-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5cb6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5cb6-105">測試給定的結果值是否等於 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="c5cb6-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="c5cb6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c5cb6-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="c5cb6-107">輸入： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="c5cb6-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="c5cb6-108">`Result` 要測試的值。</span><span class="sxs-lookup"><span data-stu-id="c5cb6-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c5cb6-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c5cb6-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c5cb6-110">`true`如果 `input` 等於，則會傳回 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="c5cb6-110">Returns `true` if `input` is equal to `Zero`.</span></span>