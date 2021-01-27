---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841000"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="81139-102">CControlled 函式</span><span class="sxs-lookup"><span data-stu-id="81139-102">CControlled function</span></span>

<span data-ttu-id="81139-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="81139-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="81139-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81139-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81139-105">在指定作業作業的情況下，會傳回新的作業，如果傳統的控制項位為 true，就會套用 op。</span><span class="sxs-lookup"><span data-stu-id="81139-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="81139-106">如果為，則不 `false` 會發生任何事。</span><span class="sxs-lookup"><span data-stu-id="81139-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="81139-107">輸入</span><span class="sxs-lookup"><span data-stu-id="81139-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="81139-108">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81139-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="81139-109">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="81139-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="81139-110">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，t) => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81139-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="81139-111">如果傳統控制位為 true，則為 op 的新作業。</span><span class="sxs-lookup"><span data-stu-id="81139-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="81139-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="81139-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="81139-113">不要</span><span class="sxs-lookup"><span data-stu-id="81139-113">'T</span></span>

<span data-ttu-id="81139-114">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="81139-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="81139-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="81139-115">See Also</span></span>

- [<span data-ttu-id="81139-116">Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="81139-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="81139-117">Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="81139-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="81139-118">Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="81139-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)