---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841878"
---
# <a name="applyif-operation"></a><span data-ttu-id="eb86b-102">ApplyIf 操作</span><span class="sxs-lookup"><span data-stu-id="eb86b-102">ApplyIf operation</span></span>

<span data-ttu-id="eb86b-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb86b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb86b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb86b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb86b-105">在傳統位上套用條件運算。</span><span class="sxs-lookup"><span data-stu-id="eb86b-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="eb86b-106">描述</span><span class="sxs-lookup"><span data-stu-id="eb86b-106">Description</span></span>

<span data-ttu-id="eb86b-107">指定作業 `op` 和位值時 `bit` ， `op` 如果是，則 `target` 會套用至 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="eb86b-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="eb86b-108">如果 `false` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="eb86b-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="eb86b-109">輸入</span><span class="sxs-lookup"><span data-stu-id="eb86b-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="eb86b-110">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb86b-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eb86b-111">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="eb86b-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="eb86b-112">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eb86b-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eb86b-113">此為布林值，可控制是否要套用 op。</span><span class="sxs-lookup"><span data-stu-id="eb86b-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="eb86b-114">目標： t</span><span class="sxs-lookup"><span data-stu-id="eb86b-114">target : 'T</span></span>

<span data-ttu-id="eb86b-115">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="eb86b-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb86b-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb86b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eb86b-117">類型參數</span><span class="sxs-lookup"><span data-stu-id="eb86b-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb86b-118">不要</span><span class="sxs-lookup"><span data-stu-id="eb86b-118">'T</span></span>

<span data-ttu-id="eb86b-119">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="eb86b-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="eb86b-120">範例</span><span class="sxs-lookup"><span data-stu-id="eb86b-120">Example</span></span>

<span data-ttu-id="eb86b-121">下列程式會將量子位登錄為計算基礎狀態，並以指定為值陣列的傳統位字串表示 `Bool` ：</span><span class="sxs-lookup"><span data-stu-id="eb86b-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="eb86b-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eb86b-122">See Also</span></span>

- [<span data-ttu-id="eb86b-123">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="eb86b-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="eb86b-124">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="eb86b-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="eb86b-125">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="eb86b-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)