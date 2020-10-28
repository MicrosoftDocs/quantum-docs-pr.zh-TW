---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698178"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="140c7-102">AllowAtMostNCallsCA 操作</span><span class="sxs-lookup"><span data-stu-id="140c7-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="140c7-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="140c7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="140c7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="140c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="140c7-105">在呼叫此作業和其 adjoint 之間，判斷指定的作業最多隻會呼叫一次特定的次數。</span><span class="sxs-lookup"><span data-stu-id="140c7-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="140c7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="140c7-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="140c7-107">nTimes： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="140c7-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="140c7-108">可能呼叫的最大次數 `op` 。</span><span class="sxs-lookup"><span data-stu-id="140c7-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="140c7-109">op： ' TInput => ' Toutput> 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="140c7-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="140c7-110">要限制其呼叫的作業。</span><span class="sxs-lookup"><span data-stu-id="140c7-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="140c7-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="140c7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="140c7-112">失敗時要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="140c7-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="140c7-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="140c7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="140c7-114">類型參數</span><span class="sxs-lookup"><span data-stu-id="140c7-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="140c7-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="140c7-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="140c7-116">' Toutput></span><span class="sxs-lookup"><span data-stu-id="140c7-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="140c7-117">備註</span><span class="sxs-lookup"><span data-stu-id="140c7-117">Remarks</span></span>

<span data-ttu-id="140c7-118">在不支援此作業的目標上，此作業可能會取代為無作業。</span><span class="sxs-lookup"><span data-stu-id="140c7-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>