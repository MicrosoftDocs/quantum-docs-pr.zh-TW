---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: e33d25899580a127171fb45a92d77cfdb5003a21
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201898"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="c136c-102">EqualityFactC 函式</span><span class="sxs-lookup"><span data-stu-id="c136c-102">EqualityFactC function</span></span>

<span data-ttu-id="c136c-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c136c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c136c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c136c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c136c-105">判斷複數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="c136c-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="c136c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c136c-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="c136c-107">實際： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="c136c-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="c136c-108">要檢查的值。</span><span class="sxs-lookup"><span data-stu-id="c136c-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="c136c-109">預期： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="c136c-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="c136c-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="c136c-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="c136c-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c136c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c136c-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="c136c-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c136c-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c136c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

