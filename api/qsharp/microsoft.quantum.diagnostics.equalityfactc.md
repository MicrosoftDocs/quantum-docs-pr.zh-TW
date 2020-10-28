---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698098"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="7375c-102">EqualityFactC 函式</span><span class="sxs-lookup"><span data-stu-id="7375c-102">EqualityFactC function</span></span>

<span data-ttu-id="7375c-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7375c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7375c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7375c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7375c-105">判斷複數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="7375c-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7375c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7375c-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="7375c-107">實際： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="7375c-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="7375c-108">要檢查的值。</span><span class="sxs-lookup"><span data-stu-id="7375c-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="7375c-109">預期： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="7375c-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="7375c-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="7375c-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="7375c-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7375c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7375c-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="7375c-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7375c-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7375c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

