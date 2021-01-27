---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844993"
---
# <a name="applyifca-operation"></a><span data-ttu-id="90839-102">ApplyIfCA 操作</span><span class="sxs-lookup"><span data-stu-id="90839-102">ApplyIfCA operation</span></span>

<span data-ttu-id="90839-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="90839-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="90839-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90839-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90839-105">針對傳統位套用條件的單一作業。</span><span class="sxs-lookup"><span data-stu-id="90839-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="90839-106">描述</span><span class="sxs-lookup"><span data-stu-id="90839-106">Description</span></span>

<span data-ttu-id="90839-107">指定作業 `op` 和位值時 `bit` ， `op` 如果是，則 `target` 會套用至 `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="90839-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="90839-108">如果 `false` 為，則不會發生任何事 `target` 。</span><span class="sxs-lookup"><span data-stu-id="90839-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="90839-109">尾碼 `CA` 表示要套用的作業是單一 (可控制和 adjointable) 。</span><span class="sxs-lookup"><span data-stu-id="90839-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="90839-110">輸入</span><span class="sxs-lookup"><span data-stu-id="90839-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="90839-111">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="90839-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="90839-112">有條件地套用的作業。</span><span class="sxs-lookup"><span data-stu-id="90839-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="90839-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90839-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90839-114">此為布林值，可控制是否要套用 op。</span><span class="sxs-lookup"><span data-stu-id="90839-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="90839-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="90839-115">target : 'T</span></span>

<span data-ttu-id="90839-116">要套用作業的輸入。</span><span class="sxs-lookup"><span data-stu-id="90839-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90839-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90839-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="90839-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="90839-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="90839-119">不要</span><span class="sxs-lookup"><span data-stu-id="90839-119">'T</span></span>

<span data-ttu-id="90839-120">要有條件地套用之作業的輸入類型。</span><span class="sxs-lookup"><span data-stu-id="90839-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="90839-121">範例</span><span class="sxs-lookup"><span data-stu-id="90839-121">Example</span></span>

<span data-ttu-id="90839-122">下列程式會將量子位登錄為計算基礎狀態，並以指定為值陣列的傳統位字串表示 `Bool` ：</span><span class="sxs-lookup"><span data-stu-id="90839-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="90839-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="90839-123">See Also</span></span>

- [<span data-ttu-id="90839-124">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="90839-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="90839-125">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="90839-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="90839-126">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="90839-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)