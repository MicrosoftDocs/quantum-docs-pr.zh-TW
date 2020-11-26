---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 3fbe000202abbd8a206b0c83dfa35f4546ea91cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202442"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="c036f-102">AssertMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="c036f-102">AssertMeasurement operation</span></span>

<span data-ttu-id="c036f-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c036f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c036f-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c036f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c036f-105">以指定的 Pauli 為基礎測量指定量子位的判斷提示，一定會有指定的結果。</span><span class="sxs-lookup"><span data-stu-id="c036f-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c036f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c036f-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="c036f-107">基底： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="c036f-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="c036f-108">用來判斷提示之機率的測量效果，以多量子位 Pauli 運算子表示。</span><span class="sxs-lookup"><span data-stu-id="c036f-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c036f-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c036f-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c036f-110">要在其上進行判斷提示的註冊。</span><span class="sxs-lookup"><span data-stu-id="c036f-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="c036f-111">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="c036f-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="c036f-112">的預期結果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="c036f-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="c036f-113">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c036f-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c036f-114">判斷提示失敗時要報告的訊息。</span><span class="sxs-lookup"><span data-stu-id="c036f-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c036f-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c036f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c036f-116">備註</span><span class="sxs-lookup"><span data-stu-id="c036f-116">Remarks</span></span>

<span data-ttu-id="c036f-117">請注意，此作業的 Adjoint 和受控制版本將不會檢查條件。</span><span class="sxs-lookup"><span data-stu-id="c036f-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="c036f-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c036f-118">See Also</span></span>

- [<span data-ttu-id="c036f-119">AssertMeasurementProbability。</span><span class="sxs-lookup"><span data-stu-id="c036f-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)