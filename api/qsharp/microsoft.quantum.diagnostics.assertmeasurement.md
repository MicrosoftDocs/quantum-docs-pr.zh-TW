---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698170"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="851c2-102">AssertMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="851c2-102">AssertMeasurement operation</span></span>

<span data-ttu-id="851c2-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="851c2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="851c2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="851c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="851c2-105">以指定的 Pauli 為基礎測量指定量子位的判斷提示，一定會有指定的結果。</span><span class="sxs-lookup"><span data-stu-id="851c2-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="851c2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="851c2-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="851c2-107">基底： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="851c2-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="851c2-108">用來判斷提示之機率的測量效果，以多量子位 Pauli 運算子表示。</span><span class="sxs-lookup"><span data-stu-id="851c2-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="851c2-109">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="851c2-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="851c2-110">要在其上進行判斷提示的註冊。</span><span class="sxs-lookup"><span data-stu-id="851c2-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="851c2-111">結果： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="851c2-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="851c2-112">的預期結果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="851c2-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="851c2-113">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="851c2-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="851c2-114">判斷提示失敗時要報告的訊息。</span><span class="sxs-lookup"><span data-stu-id="851c2-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="851c2-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="851c2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="851c2-116">備註</span><span class="sxs-lookup"><span data-stu-id="851c2-116">Remarks</span></span>

<span data-ttu-id="851c2-117">請注意，此作業的 Adjoint 和受控制版本將不會檢查條件。</span><span class="sxs-lookup"><span data-stu-id="851c2-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="851c2-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="851c2-118">See Also</span></span>

- [<span data-ttu-id="851c2-119">AssertMeasurementProbability。</span><span class="sxs-lookup"><span data-stu-id="851c2-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)