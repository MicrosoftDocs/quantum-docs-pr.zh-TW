---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829181"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="797da-102">EqualityFactCP 函式</span><span class="sxs-lookup"><span data-stu-id="797da-102">EqualityFactCP function</span></span>

<span data-ttu-id="797da-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="797da-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="797da-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="797da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="797da-105">判斷複數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="797da-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="797da-106">輸入</span><span class="sxs-lookup"><span data-stu-id="797da-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="797da-107">實際： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="797da-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="797da-108">要檢查的值。</span><span class="sxs-lookup"><span data-stu-id="797da-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="797da-109">預期： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="797da-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="797da-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="797da-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="797da-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="797da-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="797da-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="797da-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="797da-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="797da-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

