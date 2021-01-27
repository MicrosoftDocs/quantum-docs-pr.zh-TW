---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855143"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="a0271-102">RequiresCapability 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="a0271-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="a0271-103">命名空間： [Microsoft 量子. 目標](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="a0271-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="a0271-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a0271-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a0271-105">編譯器可辨識的屬性，可用來將所需的執行時間功能標示為可呼叫。</span><span class="sxs-lookup"><span data-stu-id="a0271-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="a0271-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="a0271-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="a0271-107">層級： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a0271-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a0271-108">可呼叫所需的執行時間功能層級名稱。</span><span class="sxs-lookup"><span data-stu-id="a0271-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="a0271-109">原因： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a0271-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a0271-110">說明可呼叫的原因為何需要此執行時間功能。</span><span class="sxs-lookup"><span data-stu-id="a0271-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0271-111">備註</span><span class="sxs-lookup"><span data-stu-id="a0271-111">Remarks</span></span>

<span data-ttu-id="a0271-112">這個屬性會由編譯器自動新增至 callables，除非這個屬性的實例已經存在於可呼叫的上。</span><span class="sxs-lookup"><span data-stu-id="a0271-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="a0271-113">除非在罕見的情況下，編譯器無法正確推斷所需的功能，否則不應使用它。</span><span class="sxs-lookup"><span data-stu-id="a0271-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="a0271-114">以下是功能層級名稱的清單，依提高功能或減少限制的順序：</span><span class="sxs-lookup"><span data-stu-id="a0271-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="a0271-115">測量結果無法針對相等進行比較。</span><span class="sxs-lookup"><span data-stu-id="a0271-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="a0271-116">測量結果只能在作業的 if 語句條件運算式中比較是否相等。</span><span class="sxs-lookup"><span data-stu-id="a0271-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="a0271-117">相依于結果的 if 語句區塊，不能包含在區塊外宣告之可變動變數的 set 語句，或是 return 語句。</span><span class="sxs-lookup"><span data-stu-id="a0271-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="a0271-118">無執行時間限制。</span><span class="sxs-lookup"><span data-stu-id="a0271-118">No runtime restrictions.</span></span> <span data-ttu-id="a0271-119">任何 Q # 程式都可以執行。</span><span class="sxs-lookup"><span data-stu-id="a0271-119">Any Q# program can be executed.</span></span>