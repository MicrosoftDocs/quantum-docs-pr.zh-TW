---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201796"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="5d6ec-102">EqualityFactL 函式</span><span class="sxs-lookup"><span data-stu-id="5d6ec-102">EqualityFactL function</span></span>

<span data-ttu-id="5d6ec-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5d6ec-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5d6ec-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d6ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d6ec-105">判斷提示傳統 BigInt 變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="5d6ec-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="5d6ec-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5d6ec-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="5d6ec-107">實際： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5d6ec-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5d6ec-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="5d6ec-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="5d6ec-109">預期： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5d6ec-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5d6ec-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="5d6ec-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="5d6ec-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5d6ec-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5d6ec-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="5d6ec-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d6ec-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d6ec-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

