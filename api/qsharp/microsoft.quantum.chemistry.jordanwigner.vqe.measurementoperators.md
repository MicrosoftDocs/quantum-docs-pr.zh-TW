---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698354"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="94520-102">MeasurementOperators 函式</span><span class="sxs-lookup"><span data-stu-id="94520-102">MeasurementOperators function</span></span>

<span data-ttu-id="94520-103">命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="94520-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="94520-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94520-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94520-105">計算計算 Jordan-Wigner 詞彙的預期時，所需的所有測量運算子。</span><span class="sxs-lookup"><span data-stu-id="94520-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="94520-106">輸入</span><span class="sxs-lookup"><span data-stu-id="94520-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="94520-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="94520-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="94520-108">模擬分子系統所需的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="94520-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="94520-109">索引： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="94520-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="94520-110">陣列，其中包含每個 Pauli 運算子適用的量子位索引。</span><span class="sxs-lookup"><span data-stu-id="94520-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="94520-111">termType： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="94520-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="94520-112">Jordan-Wigner 詞彙的型別。</span><span class="sxs-lookup"><span data-stu-id="94520-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="94520-113">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="94520-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="94520-114">度量運算子的陣列 (每個都是 Pauli) 的陣列。</span><span class="sxs-lookup"><span data-stu-id="94520-114">An array of measurement operators (each being an array of Pauli).</span></span>