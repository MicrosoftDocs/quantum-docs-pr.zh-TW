---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698090"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="57820-102">EqualityFactL 函式</span><span class="sxs-lookup"><span data-stu-id="57820-102">EqualityFactL function</span></span>

<span data-ttu-id="57820-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="57820-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="57820-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="57820-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="57820-105">判斷提示傳統 BigInt 變數具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="57820-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="57820-106">輸入</span><span class="sxs-lookup"><span data-stu-id="57820-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="57820-107">實際： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="57820-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="57820-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="57820-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="57820-109">預期： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="57820-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="57820-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="57820-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="57820-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="57820-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="57820-112">觸發判斷提示時要使用的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="57820-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57820-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57820-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

