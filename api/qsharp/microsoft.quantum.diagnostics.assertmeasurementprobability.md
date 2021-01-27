---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830829"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="72249-102">AssertMeasurementProbability 操作</span><span class="sxs-lookup"><span data-stu-id="72249-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="72249-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="72249-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="72249-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="72249-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="72249-105">以指定的 Pauli 為基礎來測量指定量子位的判斷提示，在部分容錯範圍內會有給定機率的指定結果。</span><span class="sxs-lookup"><span data-stu-id="72249-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="72249-106">輸入</span><span class="sxs-lookup"><span data-stu-id="72249-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="72249-107">基底： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="72249-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="72249-108">用來判斷提示之機率的測量效果，以多量子位 Pauli 運算子表示。</span><span class="sxs-lookup"><span data-stu-id="72249-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="72249-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="72249-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="72249-110">要在其上進行判斷提示的註冊。</span><span class="sxs-lookup"><span data-stu-id="72249-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="72249-111">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="72249-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="72249-112">的預期結果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="72249-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="72249-113">prob： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="72249-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="72249-114">預期指定結果的機率。</span><span class="sxs-lookup"><span data-stu-id="72249-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="72249-115">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="72249-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="72249-116">判斷提示失敗時要報告的訊息。</span><span class="sxs-lookup"><span data-stu-id="72249-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="72249-117">tol： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="72249-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="72249-118">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72249-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="72249-119">範例</span><span class="sxs-lookup"><span data-stu-id="72249-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="72249-120">備註</span><span class="sxs-lookup"><span data-stu-id="72249-120">Remarks</span></span>

<span data-ttu-id="72249-121">請注意，此作業的 Adjoint 和受控制版本將不會檢查條件。</span><span class="sxs-lookup"><span data-stu-id="72249-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="72249-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="72249-122">See Also</span></span>

- [<span data-ttu-id="72249-123">AssertMeasurement。</span><span class="sxs-lookup"><span data-stu-id="72249-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)