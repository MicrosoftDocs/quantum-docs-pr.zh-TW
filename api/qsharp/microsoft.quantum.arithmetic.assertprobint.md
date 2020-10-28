---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699947"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="ad31d-102">AssertProbInt 操作</span><span class="sxs-lookup"><span data-stu-id="ad31d-102">AssertProbInt operation</span></span>

<span data-ttu-id="ad31d-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ad31d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ad31d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ad31d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ad31d-105">判斷量子暫存器特定狀態的機率具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="ad31d-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="ad31d-106">描述</span><span class="sxs-lookup"><span data-stu-id="ad31d-106">Description</span></span>

<span data-ttu-id="ad31d-107">假設有 $n $-量子位量子 state $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ Alpha_j \ket{j} $，判斷提示 $ \ket{j} $j $ 的機率 $ | \ Alpha_j | ^ 2 $ 具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="ad31d-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="ad31d-108">輸入</span><span class="sxs-lookup"><span data-stu-id="ad31d-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="ad31d-109">stateIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad31d-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad31d-110">索引 $j $ 表示由暫存器表示的狀態 $ \ket{j} $ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="ad31d-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="ad31d-111">預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ad31d-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ad31d-112">$ | \ Alpha_j | ^ 2 $ 的預期值。</span><span class="sxs-lookup"><span data-stu-id="ad31d-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="ad31d-113">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ad31d-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ad31d-114">以位元組由大到小的格式儲存 $ \ket{\psi} $ 的量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="ad31d-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="ad31d-115">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ad31d-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ad31d-116">實際和預期之間差異的絕對容錯。</span><span class="sxs-lookup"><span data-stu-id="ad31d-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad31d-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad31d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

