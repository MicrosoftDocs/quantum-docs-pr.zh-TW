---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201915"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="c321f-102">EqualityFactB 函式</span><span class="sxs-lookup"><span data-stu-id="c321f-102">EqualityFactB function</span></span>

<span data-ttu-id="c321f-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c321f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c321f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c321f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c321f-105">判斷提示傳統 Bool 變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="c321f-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="c321f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c321f-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="c321f-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c321f-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c321f-108">要檢查的變數。</span><span class="sxs-lookup"><span data-stu-id="c321f-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="c321f-109">預期： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c321f-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c321f-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="c321f-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="c321f-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c321f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c321f-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="c321f-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c321f-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c321f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

