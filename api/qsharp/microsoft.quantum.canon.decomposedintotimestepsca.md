---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699044"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="5338c-102">DecomposedIntoTimeStepsCA 函式</span><span class="sxs-lookup"><span data-stu-id="5338c-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="5338c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5338c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5338c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5338c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5338c-105">傳回對指定作業執行 Trotter – Suzuki 整合器的作業。</span><span class="sxs-lookup"><span data-stu-id="5338c-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="5338c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5338c-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="5338c-107">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5338c-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5338c-108">要分解為時間步驟的作業數目。</span><span class="sxs-lookup"><span data-stu-id="5338c-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="5338c-109">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="5338c-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5338c-110">一種作業，可接受索引輸入 (類型 `Int`) 和時間輸入 (類型 `Double`) 以進行分解。</span><span class="sxs-lookup"><span data-stu-id="5338c-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="5338c-111">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5338c-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5338c-112">選取要使用的 Trotter-Suzuki 整合器順序。</span><span class="sxs-lookup"><span data-stu-id="5338c-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="5338c-113">Order 1 甚至訂單2，4，6,.。。目前支援。</span><span class="sxs-lookup"><span data-stu-id="5338c-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="5338c-114">輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="5338c-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5338c-115">傳回實 Trotter – Suzuki 整合器的單一參數，其中第一個參數 `Double` 是整合步驟的大小，而第二個參數則是採取動作的目標。</span><span class="sxs-lookup"><span data-stu-id="5338c-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5338c-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="5338c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5338c-117">不要</span><span class="sxs-lookup"><span data-stu-id="5338c-117">'T</span></span>

<span data-ttu-id="5338c-118">每次步驟應採取的型別;通常是 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="5338c-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5338c-119">備註</span><span class="sxs-lookup"><span data-stu-id="5338c-119">Remarks</span></span>

<span data-ttu-id="5338c-120">以等於的呼叫時 `order` `1` ，此函式會傳回可由最低順序的 Trotter – Suzuki 整合者 $ $ \begin{align} S_1 ( \lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda} 的運算 \end{align} $ $，我們已遵循 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) 的標記法，並讓 $ \lambda $ 成為所傳回作業的第一個輸入所表示的演進時間 () ，並讓 let $ \{ H_j \} _ {j = 1} ^ {m} $ 成為一組 (扭曲-Hermitian) 要整合的 dynamical 產生器，這 `op(j, lambda, _)` 是由單一運算子 $e ^ {H_j \lambda} $ 所模擬。</span><span class="sxs-lookup"><span data-stu-id="5338c-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="5338c-121">同樣地， `order` 的會傳回 `2` 第二個順序的對稱 Trotter – Suzuki 整合者 $ $ \begin{align} S_2 ( \lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}。</span><span class="sxs-lookup"><span data-stu-id="5338c-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="5338c-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5338c-122">\end{align} $$</span></span>

<span data-ttu-id="5338c-123">更高的值 `order` 會使用 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)的遞迴結構來執行。</span><span class="sxs-lookup"><span data-stu-id="5338c-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="5338c-124">參考</span><span class="sxs-lookup"><span data-stu-id="5338c-124">References</span></span>

- [<span data-ttu-id="5338c-125">*D. Berry、G. Ahokas、Cleve、b. Sanders*</span><span class="sxs-lookup"><span data-stu-id="5338c-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)