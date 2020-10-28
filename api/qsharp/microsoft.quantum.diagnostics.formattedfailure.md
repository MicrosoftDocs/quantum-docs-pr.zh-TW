---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698067"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="bd0e8-102">FormattedFailure 函式</span><span class="sxs-lookup"><span data-stu-id="bd0e8-102">FormattedFailure function</span></span>

<span data-ttu-id="bd0e8-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bd0e8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bd0e8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd0e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd0e8-105">內建函式用來因有意義的錯誤訊息而失敗。</span><span class="sxs-lookup"><span data-stu-id="bd0e8-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bd0e8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bd0e8-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="bd0e8-107">實際： t</span><span class="sxs-lookup"><span data-stu-id="bd0e8-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="bd0e8-108">預期： t</span><span class="sxs-lookup"><span data-stu-id="bd0e8-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="bd0e8-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bd0e8-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="bd0e8-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd0e8-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bd0e8-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="bd0e8-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd0e8-112">不要</span><span class="sxs-lookup"><span data-stu-id="bd0e8-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="bd0e8-113">備註</span><span class="sxs-lookup"><span data-stu-id="bd0e8-113">Remarks</span></span>

<span data-ttu-id="bd0e8-114">此函式的目的是要由模擬執行時間模擬，以便允許轉送格式化您一致。</span><span class="sxs-lookup"><span data-stu-id="bd0e8-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>