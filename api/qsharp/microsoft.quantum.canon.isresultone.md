---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: f259c21e6cc0a4886332e9ffcb546e527ec7def1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840336"
---
# <a name="isresultone-function"></a><span data-ttu-id="bd2e2-102">IsResultOne 函式</span><span class="sxs-lookup"><span data-stu-id="bd2e2-102">IsResultOne function</span></span>

<span data-ttu-id="bd2e2-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd2e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd2e2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd2e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd2e2-105">測試給定的結果值是否等於 `One` 。</span><span class="sxs-lookup"><span data-stu-id="bd2e2-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="bd2e2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bd2e2-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="bd2e2-107">輸入：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="bd2e2-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="bd2e2-108">`Result` 要測試的值。</span><span class="sxs-lookup"><span data-stu-id="bd2e2-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bd2e2-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bd2e2-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bd2e2-110">`true`如果 `input` 等於，則會傳回 `One` 。</span><span class="sxs-lookup"><span data-stu-id="bd2e2-110">Returns `true` if `input` is equal to `One`.</span></span>