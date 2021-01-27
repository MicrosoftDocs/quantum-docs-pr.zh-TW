---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828268"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="b5d52-102">FormattedFailure 函式</span><span class="sxs-lookup"><span data-stu-id="b5d52-102">FormattedFailure function</span></span>

<span data-ttu-id="b5d52-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b5d52-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b5d52-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5d52-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5d52-105">內建函式用來因有意義的錯誤訊息而失敗。</span><span class="sxs-lookup"><span data-stu-id="b5d52-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b5d52-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b5d52-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="b5d52-107">實際： t</span><span class="sxs-lookup"><span data-stu-id="b5d52-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="b5d52-108">預期： t</span><span class="sxs-lookup"><span data-stu-id="b5d52-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="b5d52-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b5d52-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b5d52-110">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5d52-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b5d52-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="b5d52-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5d52-112">不要</span><span class="sxs-lookup"><span data-stu-id="b5d52-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b5d52-113">備註</span><span class="sxs-lookup"><span data-stu-id="b5d52-113">Remarks</span></span>

<span data-ttu-id="b5d52-114">此函式的目的是要由模擬執行時間模擬，以便允許轉送格式化您一致。</span><span class="sxs-lookup"><span data-stu-id="b5d52-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>