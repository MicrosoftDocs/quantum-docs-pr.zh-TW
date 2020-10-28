---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698367"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="69b25-102">EstimateTermExpectation 操作</span><span class="sxs-lookup"><span data-stu-id="69b25-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="69b25-103">命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="69b25-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="69b25-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69b25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69b25-105">計算與指定 Jordan-Wigner Hamiltonian 期限相關聯的能源</span><span class="sxs-lookup"><span data-stu-id="69b25-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="69b25-106">描述</span><span class="sxs-lookup"><span data-stu-id="69b25-106">Description</span></span>

<span data-ttu-id="69b25-107">這項作業會評估與每個測量運算子相關聯的預期值，並使用取樣來乘以對應的係數。</span><span class="sxs-lookup"><span data-stu-id="69b25-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="69b25-108">結果會匯總到包含 Jordan-Wigner 期限能源的變數中。</span><span class="sxs-lookup"><span data-stu-id="69b25-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="69b25-109">輸入</span><span class="sxs-lookup"><span data-stu-id="69b25-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="69b25-110">inputStateUnitary： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="69b25-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="69b25-111">用於狀態準備的單一。</span><span class="sxs-lookup"><span data-stu-id="69b25-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="69b25-112">ops： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="69b25-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="69b25-113">Jordan-Wigner 詞彙的測量運算子。</span><span class="sxs-lookup"><span data-stu-id="69b25-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="69b25-114">coeffs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="69b25-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="69b25-115">Jordan-Wigner 詞彙的係數。</span><span class="sxs-lookup"><span data-stu-id="69b25-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="69b25-116">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69b25-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69b25-117">模擬分子系統所需的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="69b25-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="69b25-118">nSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69b25-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69b25-119">要用於估計預期詞彙的樣本數目。</span><span class="sxs-lookup"><span data-stu-id="69b25-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="69b25-120">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="69b25-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="69b25-121">與 Jordan-Wigner 詞彙相關聯的能源。</span><span class="sxs-lookup"><span data-stu-id="69b25-121">The energy associated to the Jordan-Wigner term.</span></span>