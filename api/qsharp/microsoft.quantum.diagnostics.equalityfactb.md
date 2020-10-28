---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698095"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="2c5cd-102">EqualityFactB 函式</span><span class="sxs-lookup"><span data-stu-id="2c5cd-102">EqualityFactB function</span></span>

<span data-ttu-id="2c5cd-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2c5cd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2c5cd-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c5cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c5cd-105">判斷提示傳統 Bool 變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="2c5cd-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2c5cd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2c5cd-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2c5cd-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2c5cd-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2c5cd-108">要檢查的變數。</span><span class="sxs-lookup"><span data-stu-id="2c5cd-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="2c5cd-109">預期： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2c5cd-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2c5cd-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="2c5cd-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2c5cd-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2c5cd-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2c5cd-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="2c5cd-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c5cd-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c5cd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

