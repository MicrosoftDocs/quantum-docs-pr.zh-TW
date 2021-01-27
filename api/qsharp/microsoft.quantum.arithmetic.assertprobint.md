---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843412"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="82a7c-102">AssertProbInt 操作</span><span class="sxs-lookup"><span data-stu-id="82a7c-102">AssertProbInt operation</span></span>

<span data-ttu-id="82a7c-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="82a7c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="82a7c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="82a7c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="82a7c-105">判斷量子暫存器特定狀態的機率具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="82a7c-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="82a7c-106">描述</span><span class="sxs-lookup"><span data-stu-id="82a7c-106">Description</span></span>

<span data-ttu-id="82a7c-107">假設有 $n $-量子位量子 state $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ Alpha_j \ket{j} $，判斷提示 $ \ket{j} $j $ 的機率 $ | \ Alpha_j | ^ 2 $ 具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="82a7c-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="82a7c-108">輸入</span><span class="sxs-lookup"><span data-stu-id="82a7c-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="82a7c-109">stateIndex： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82a7c-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82a7c-110">索引 $j $ 表示由暫存器表示的狀態 $ \ket{j} $ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="82a7c-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="82a7c-111">預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="82a7c-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="82a7c-112">$ | \ Alpha_j | ^ 2 $ 的預期值。</span><span class="sxs-lookup"><span data-stu-id="82a7c-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="82a7c-113">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="82a7c-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="82a7c-114">以位元組由大到小的格式儲存 $ \ket{\psi} $ 的量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="82a7c-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="82a7c-115">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="82a7c-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="82a7c-116">實際和預期之間差異的絕對容錯。</span><span class="sxs-lookup"><span data-stu-id="82a7c-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82a7c-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82a7c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="82a7c-118">範例</span><span class="sxs-lookup"><span data-stu-id="82a7c-118">Example</span></span>

<span data-ttu-id="82a7c-119">假設註冊會 `qubits` 以位元組由小到大的格式，將3量子位的量子狀態 $ \ket{\psi} = \ sqrt {1/8} \ ket {0} + \ sqrt {7/8} \ ket {6} $ 編碼。</span><span class="sxs-lookup"><span data-stu-id="82a7c-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="82a7c-120">這表示 number 狀態 $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ 和 $ \ket {6} \equiv\ket {0} \ket {1} \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="82a7c-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="82a7c-121">然後，下列判斷提示會成功：</span><span class="sxs-lookup"><span data-stu-id="82a7c-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```