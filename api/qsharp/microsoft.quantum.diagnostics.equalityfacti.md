---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853341"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="60bbe-102">EqualityFactI 函式</span><span class="sxs-lookup"><span data-stu-id="60bbe-102">EqualityFactI function</span></span>

<span data-ttu-id="60bbe-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="60bbe-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="60bbe-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60bbe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60bbe-105">判斷提示傳統 Int 變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="60bbe-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="60bbe-106">輸入</span><span class="sxs-lookup"><span data-stu-id="60bbe-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="60bbe-107">實際： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="60bbe-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="60bbe-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="60bbe-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="60bbe-109">預期： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="60bbe-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="60bbe-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="60bbe-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="60bbe-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="60bbe-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="60bbe-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="60bbe-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60bbe-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60bbe-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

