---
uid: Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates
title: EstimateRealOverlapBetweenStates 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateRealOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 1448e760294e958b152f4ceb3faf979441ca986d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851846"
---
# <a name="estimaterealoverlapbetweenstates-operation"></a><span data-ttu-id="1da7b-102">EstimateRealOverlapBetweenStates 操作</span><span class="sxs-lookup"><span data-stu-id="1da7b-102">EstimateRealOverlapBetweenStates operation</span></span>

<span data-ttu-id="1da7b-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1da7b-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1da7b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1da7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1da7b-105">假設有兩個作業，每個作業都會準備狀態的複本，並估計每個作業所準備的狀態之間重迭的實際部分。</span><span class="sxs-lookup"><span data-stu-id="1da7b-105">Given two operations which each prepare copies of a state, estimates the real part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateRealOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="1da7b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1da7b-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="1da7b-107">commonPreparation： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="1da7b-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="1da7b-108">準備固定輸入狀態的作業。</span><span class="sxs-lookup"><span data-stu-id="1da7b-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="1da7b-109">preparation1： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1da7b-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1da7b-110">要比較的兩個狀態準備作業中的第一個。</span><span class="sxs-lookup"><span data-stu-id="1da7b-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="1da7b-111">preparation2： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1da7b-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1da7b-112">要比較的兩個狀態準備作業的第二個。</span><span class="sxs-lookup"><span data-stu-id="1da7b-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="1da7b-113">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1da7b-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1da7b-114">`commonPreparation`、 `preparation1` 和所有 act 的量子位數目 `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="1da7b-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="1da7b-115">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1da7b-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1da7b-116">用來估計重迭的度量數目。</span><span class="sxs-lookup"><span data-stu-id="1da7b-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="1da7b-117">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1da7b-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="1da7b-118">備註</span><span class="sxs-lookup"><span data-stu-id="1da7b-118">Remarks</span></span>

<span data-ttu-id="1da7b-119">這項作業會使用 Hadamard 測試來尋找 $ $ \begin{align} \braket{\psi 的真實部分 |V ^ {\dagger} U |\psi} \end{align} $ $，其中 $ \ket{\psi} $ 是所準備的狀態 `commonPreparation` ，$U $ 是的動作的單一標記法 `preparation1` ，以及 $V $ 對應至的位置 `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="1da7b-119">This operation uses the Hadamard test to find the real part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="1da7b-120">參考資料</span><span class="sxs-lookup"><span data-stu-id="1da7b-120">References</span></span>

- <span data-ttu-id="1da7b-121">Aharonov *et al.exe.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096)。</span><span class="sxs-lookup"><span data-stu-id="1da7b-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="1da7b-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1da7b-122">See Also</span></span>

- [<span data-ttu-id="1da7b-123">EstimateImagOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="1da7b-123">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)
- [<span data-ttu-id="1da7b-124">EstimateOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="1da7b-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)