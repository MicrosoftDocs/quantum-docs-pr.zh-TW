---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 740461ee17bdda281a6bd8572a15d27b17be9535
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840962"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="1bdce-102">CControlledCA 函式</span><span class="sxs-lookup"><span data-stu-id="1bdce-102">CControlledCA function</span></span>

<span data-ttu-id="1bdce-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1bdce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1bdce-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1bdce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1bdce-105">在指定作業作業的情況下，會傳回新的作業，如果傳統的控制項位為 true，就會套用 op。</span><span class="sxs-lookup"><span data-stu-id="1bdce-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="1bdce-106">如果為，則不 `false` 會發生任何事。</span><span class="sxs-lookup"><span data-stu-id="1bdce-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="1bdce-107">修飾詞 `CA` 表示作業可控制且 adjointable。</span><span class="sxs-lookup"><span data-stu-id="1bdce-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="1bdce-108">輸入</span><span class="sxs-lookup"><span data-stu-id="1bdce-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="1bdce-109">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1bdce-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1bdce-110">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="1bdce-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj--ctl"></a><span data-ttu-id="1bdce-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1bdce-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1bdce-112">如果傳統控制位為 true，則為 op 的新作業。</span><span class="sxs-lookup"><span data-stu-id="1bdce-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1bdce-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="1bdce-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1bdce-114">不要</span><span class="sxs-lookup"><span data-stu-id="1bdce-114">'T</span></span>

<span data-ttu-id="1bdce-115">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="1bdce-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bdce-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1bdce-116">See Also</span></span>

- [<span data-ttu-id="1bdce-117">Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="1bdce-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)