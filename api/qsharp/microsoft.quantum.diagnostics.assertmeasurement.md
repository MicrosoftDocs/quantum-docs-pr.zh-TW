---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853493"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="d5a8d-102">AssertMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="d5a8d-102">AssertMeasurement operation</span></span>

<span data-ttu-id="d5a8d-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d5a8d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d5a8d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d5a8d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d5a8d-105">以指定的 Pauli 為基礎測量指定量子位的判斷提示，一定會有指定的結果。</span><span class="sxs-lookup"><span data-stu-id="d5a8d-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d5a8d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d5a8d-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="d5a8d-107">基底： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="d5a8d-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="d5a8d-108">用來判斷提示之機率的測量效果，以多量子位 Pauli 運算子表示。</span><span class="sxs-lookup"><span data-stu-id="d5a8d-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="d5a8d-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5a8d-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5a8d-110">要在其上進行判斷提示的註冊。</span><span class="sxs-lookup"><span data-stu-id="d5a8d-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="d5a8d-111">結果：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="d5a8d-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="d5a8d-112">的預期結果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="d5a8d-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="d5a8d-113">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d5a8d-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d5a8d-114">判斷提示失敗時要報告的訊息。</span><span class="sxs-lookup"><span data-stu-id="d5a8d-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5a8d-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5a8d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d5a8d-116">備註</span><span class="sxs-lookup"><span data-stu-id="d5a8d-116">Remarks</span></span>

<span data-ttu-id="d5a8d-117">請注意，此作業的 Adjoint 和受控制版本將不會檢查條件。</span><span class="sxs-lookup"><span data-stu-id="d5a8d-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5a8d-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d5a8d-118">See Also</span></span>

- [<span data-ttu-id="d5a8d-119">AssertMeasurementProbability。</span><span class="sxs-lookup"><span data-stu-id="d5a8d-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)