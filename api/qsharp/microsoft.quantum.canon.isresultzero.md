---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b4e9b62b20e12a8dce544ce16dcddcf15fdf2680
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206522"
---
# <a name="isresultzero-function"></a><span data-ttu-id="546be-102">IsResultZero 函式</span><span class="sxs-lookup"><span data-stu-id="546be-102">IsResultZero function</span></span>

<span data-ttu-id="546be-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="546be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="546be-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="546be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="546be-105">測試給定的結果值是否等於 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="546be-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="546be-106">輸入</span><span class="sxs-lookup"><span data-stu-id="546be-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="546be-107">輸入：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="546be-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="546be-108">`Result` 要測試的值。</span><span class="sxs-lookup"><span data-stu-id="546be-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="546be-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="546be-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="546be-110">`true`如果 `input` 等於，則會傳回 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="546be-110">Returns `true` if `input` is equal to `Zero`.</span></span>