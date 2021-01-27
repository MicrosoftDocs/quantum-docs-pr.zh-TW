---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 0fcfe553d7a0050a9ab35a43ac5fe2b1958514db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853370"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="07b49-102">EqualityFactC 函式</span><span class="sxs-lookup"><span data-stu-id="07b49-102">EqualityFactC function</span></span>

<span data-ttu-id="07b49-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="07b49-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="07b49-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07b49-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="07b49-105">判斷複數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="07b49-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="07b49-106">輸入</span><span class="sxs-lookup"><span data-stu-id="07b49-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="07b49-107">實際： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="07b49-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="07b49-108">要檢查的值。</span><span class="sxs-lookup"><span data-stu-id="07b49-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="07b49-109">預期： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="07b49-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="07b49-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="07b49-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="07b49-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="07b49-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="07b49-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="07b49-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07b49-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07b49-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

