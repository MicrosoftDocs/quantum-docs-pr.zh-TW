---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: a3e8791321b4f2ca1885dffeb92c7b13e5491a32
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698147"
---
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="4aac8-102">AssertOperationsEqualReferenced 操作</span><span class="sxs-lookup"><span data-stu-id="4aac8-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="4aac8-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4aac8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4aac8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4aac8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4aac8-105">假設有兩個作業，請判斷它們對所有輸入狀態的作用都相同。</span><span class="sxs-lookup"><span data-stu-id="4aac8-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="4aac8-106">此判斷提示是藉由使用 Choi 對於– Jamiołkowski isomorphism 來執行，將判斷提示減少到兩個纏結暫存器上的其中一個量子位狀態判斷提示。</span><span class="sxs-lookup"><span data-stu-id="4aac8-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="4aac8-107">因此，這項作業只需要對每個要測試的作業進行單一呼叫，但需要配置兩次的量子位。</span><span class="sxs-lookup"><span data-stu-id="4aac8-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="4aac8-108">您可以使用這個判斷提示來確保作業的優化版本與其全面的實作為相同，或在非量子輸入範圍中運作的作業會符合已知案例。</span><span class="sxs-lookup"><span data-stu-id="4aac8-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="4aac8-109">輸入</span><span class="sxs-lookup"><span data-stu-id="4aac8-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="4aac8-110">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4aac8-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4aac8-111">要傳遞至每個作業的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="4aac8-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="4aac8-112">實際： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4aac8-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4aac8-113">要測試的作業。</span><span class="sxs-lookup"><span data-stu-id="4aac8-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit-adj"></a><span data-ttu-id="4aac8-114">預期： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="4aac8-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4aac8-115">作業，定義受測試作業的預期行為。</span><span class="sxs-lookup"><span data-stu-id="4aac8-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4aac8-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4aac8-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4aac8-117">備註</span><span class="sxs-lookup"><span data-stu-id="4aac8-117">Remarks</span></span>

<span data-ttu-id="4aac8-118">這項作業會要求將預期行為模型化的作業 adjointable，如此一來，就可以單獨在目標暫存器上執行反向操作。</span><span class="sxs-lookup"><span data-stu-id="4aac8-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="4aac8-119">正式來說，您可以指定可放寬這項需求的轉出作業，但換位作業不是一般 realizable 的任意量子作業，因此此處不包含此選項。</span><span class="sxs-lookup"><span data-stu-id="4aac8-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>