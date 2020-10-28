---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699078"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="0b275-102">CControlledC 函式</span><span class="sxs-lookup"><span data-stu-id="0b275-102">CControlledC function</span></span>

<span data-ttu-id="0b275-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b275-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b275-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b275-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b275-105">在指定作業作業的情況下，會傳回新的作業，如果傳統的控制項位為 true，就會套用 op。</span><span class="sxs-lookup"><span data-stu-id="0b275-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="0b275-106">如果為，則不 `false` 會發生任何事。</span><span class="sxs-lookup"><span data-stu-id="0b275-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="0b275-107">修飾詞 `C` 表示作業可控制。</span><span class="sxs-lookup"><span data-stu-id="0b275-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="0b275-108">輸入</span><span class="sxs-lookup"><span data-stu-id="0b275-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="0b275-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="0b275-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0b275-110">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="0b275-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="0b275-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="0b275-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="0b275-112">如果傳統控制位為 true，則為 op 的新作業。</span><span class="sxs-lookup"><span data-stu-id="0b275-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b275-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="0b275-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b275-114">不要</span><span class="sxs-lookup"><span data-stu-id="0b275-114">'T</span></span>

<span data-ttu-id="0b275-115">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="0b275-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b275-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0b275-116">See Also</span></span>

- [<span data-ttu-id="0b275-117">Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="0b275-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)