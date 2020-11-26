---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201762"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="214c4-102">EqualityFactR 函式</span><span class="sxs-lookup"><span data-stu-id="214c4-102">EqualityFactR function</span></span>

<span data-ttu-id="214c4-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="214c4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="214c4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="214c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="214c4-105">判斷提示傳統結果變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="214c4-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="214c4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="214c4-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="214c4-107">實際：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="214c4-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="214c4-108">要檢查的變數。</span><span class="sxs-lookup"><span data-stu-id="214c4-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="214c4-109">預期：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="214c4-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="214c4-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="214c4-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="214c4-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="214c4-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="214c4-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="214c4-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="214c4-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="214c4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

