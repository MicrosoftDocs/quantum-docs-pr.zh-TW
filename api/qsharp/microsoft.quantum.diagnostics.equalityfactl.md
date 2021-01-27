---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829135"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="127dc-102">EqualityFactL 函式</span><span class="sxs-lookup"><span data-stu-id="127dc-102">EqualityFactL function</span></span>

<span data-ttu-id="127dc-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="127dc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="127dc-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="127dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="127dc-105">判斷提示傳統 BigInt 變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="127dc-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="127dc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="127dc-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="127dc-107">實際： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="127dc-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="127dc-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="127dc-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="127dc-109">預期： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="127dc-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="127dc-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="127dc-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="127dc-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="127dc-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="127dc-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="127dc-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="127dc-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="127dc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

