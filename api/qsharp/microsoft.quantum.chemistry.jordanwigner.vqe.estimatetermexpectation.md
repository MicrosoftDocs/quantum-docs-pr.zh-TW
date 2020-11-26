---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224644"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="0a96c-102">EstimateTermExpectation 操作</span><span class="sxs-lookup"><span data-stu-id="0a96c-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="0a96c-103">命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="0a96c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="0a96c-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0a96c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="0a96c-105">計算與指定 Jordan-Wigner Hamiltonian 期限相關聯的能源</span><span class="sxs-lookup"><span data-stu-id="0a96c-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="0a96c-106">描述</span><span class="sxs-lookup"><span data-stu-id="0a96c-106">Description</span></span>

<span data-ttu-id="0a96c-107">這項作業會評估與每個測量運算子相關聯的預期值，並使用取樣來乘以對應的係數。</span><span class="sxs-lookup"><span data-stu-id="0a96c-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="0a96c-108">結果會匯總到包含 Jordan-Wigner 期限能源的變數中。</span><span class="sxs-lookup"><span data-stu-id="0a96c-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="0a96c-109">輸入</span><span class="sxs-lookup"><span data-stu-id="0a96c-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="0a96c-110">inputStateUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="0a96c-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0a96c-111">用於狀態準備的單一。</span><span class="sxs-lookup"><span data-stu-id="0a96c-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="0a96c-112">ops： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="0a96c-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="0a96c-113">Jordan-Wigner 詞彙的測量運算子。</span><span class="sxs-lookup"><span data-stu-id="0a96c-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="0a96c-114">coeffs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0a96c-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0a96c-115">Jordan-Wigner 詞彙的係數。</span><span class="sxs-lookup"><span data-stu-id="0a96c-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="0a96c-116">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a96c-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a96c-117">模擬分子系統所需的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="0a96c-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="0a96c-118">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a96c-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a96c-119">要用於估計預期詞彙的樣本數目。</span><span class="sxs-lookup"><span data-stu-id="0a96c-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="0a96c-120">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0a96c-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0a96c-121">與 Jordan-Wigner 詞彙相關聯的能源。</span><span class="sxs-lookup"><span data-stu-id="0a96c-121">The energy associated to the Jordan-Wigner term.</span></span>