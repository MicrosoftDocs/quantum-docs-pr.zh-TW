---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698730"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="f1c0d-102">EstimateOverlapBetweenStates 操作</span><span class="sxs-lookup"><span data-stu-id="f1c0d-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="f1c0d-103">命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f1c0d-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="f1c0d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1c0d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1c0d-105">假設有兩個作業，每個作業都會準備狀態的複本，並估計每個作業所準備的狀態之間的平方重迭。</span><span class="sxs-lookup"><span data-stu-id="f1c0d-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="f1c0d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f1c0d-106">Input</span></span>

### <a name="preparation1--qubit--unit-adj"></a><span data-ttu-id="f1c0d-107">preparation1： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="f1c0d-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f1c0d-108">要比較的兩個狀態準備作業中的第一個。</span><span class="sxs-lookup"><span data-stu-id="f1c0d-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj"></a><span data-ttu-id="f1c0d-109">preparation2： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="f1c0d-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f1c0d-110">要比較的兩個狀態準備作業的第二個。</span><span class="sxs-lookup"><span data-stu-id="f1c0d-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="f1c0d-111">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1c0d-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1c0d-112">`commonPreparation`、 `preparation1` 和所有 act 的量子位數目 `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="f1c0d-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="f1c0d-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f1c0d-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f1c0d-114">用來估計重迭的度量數目。</span><span class="sxs-lookup"><span data-stu-id="f1c0d-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="f1c0d-115">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f1c0d-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="f1c0d-116">備註</span><span class="sxs-lookup"><span data-stu-id="f1c0d-116">Remarks</span></span>

<span data-ttu-id="f1c0d-117">這種操作會使用交換測試來尋找 $ $ \begin{align} \left |\braket{00\cdots 0 |V ^ {\dagger} U |00 \ cdots 0} \right | ^ 2 \end{align} $ $，其中 $U $ 是的動作的單一標記法 `preparation1` ，以及 $V $ 對應的位置 `preparation2` 。</span><span class="sxs-lookup"><span data-stu-id="f1c0d-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1c0d-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f1c0d-118">See Also</span></span>

- [<span data-ttu-id="f1c0d-119">EstimateRealOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="f1c0d-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="f1c0d-120">EstimateImagOverlapBetweenStates。</span><span class="sxs-lookup"><span data-stu-id="f1c0d-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)