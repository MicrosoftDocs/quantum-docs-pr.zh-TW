---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853339"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="b9a0b-102">EqualityFactR 函式</span><span class="sxs-lookup"><span data-stu-id="b9a0b-102">EqualityFactR function</span></span>

<span data-ttu-id="b9a0b-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b9a0b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b9a0b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9a0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9a0b-105">判斷提示傳統結果變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="b9a0b-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b9a0b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b9a0b-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="b9a0b-107">實際：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b9a0b-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="b9a0b-108">要檢查的變數。</span><span class="sxs-lookup"><span data-stu-id="b9a0b-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="b9a0b-109">預期：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b9a0b-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="b9a0b-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="b9a0b-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="b9a0b-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b9a0b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b9a0b-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="b9a0b-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b9a0b-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b9a0b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

