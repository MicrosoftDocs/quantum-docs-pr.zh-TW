---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698086"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="9dfa4-102">EqualityFactR 函式</span><span class="sxs-lookup"><span data-stu-id="9dfa4-102">EqualityFactR function</span></span>

<span data-ttu-id="9dfa4-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9dfa4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9dfa4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9dfa4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9dfa4-105">判斷提示傳統結果變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="9dfa4-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="9dfa4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9dfa4-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="9dfa4-107">實際： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9dfa4-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="9dfa4-108">要檢查的變數。</span><span class="sxs-lookup"><span data-stu-id="9dfa4-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="9dfa4-109">預期： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9dfa4-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="9dfa4-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="9dfa4-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="9dfa4-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9dfa4-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9dfa4-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="9dfa4-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9dfa4-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9dfa4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

