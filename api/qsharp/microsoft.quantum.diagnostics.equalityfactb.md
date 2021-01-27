---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829213"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="d8591-102">EqualityFactB 函式</span><span class="sxs-lookup"><span data-stu-id="d8591-102">EqualityFactB function</span></span>

<span data-ttu-id="d8591-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d8591-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d8591-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8591-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8591-105">判斷提示傳統 Bool 變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="d8591-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d8591-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d8591-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="d8591-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d8591-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d8591-108">要檢查的變數。</span><span class="sxs-lookup"><span data-stu-id="d8591-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="d8591-109">預期： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d8591-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d8591-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="d8591-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="d8591-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d8591-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d8591-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="d8591-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8591-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8591-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

