---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698094"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="2cc51-102">EqualityFactCP 函式</span><span class="sxs-lookup"><span data-stu-id="2cc51-102">EqualityFactCP function</span></span>

<span data-ttu-id="2cc51-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2cc51-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2cc51-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2cc51-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2cc51-105">判斷複數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="2cc51-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2cc51-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2cc51-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="2cc51-107">實際： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2cc51-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2cc51-108">要檢查的值。</span><span class="sxs-lookup"><span data-stu-id="2cc51-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="2cc51-109">預期： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="2cc51-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="2cc51-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="2cc51-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2cc51-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2cc51-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2cc51-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="2cc51-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2cc51-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cc51-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

