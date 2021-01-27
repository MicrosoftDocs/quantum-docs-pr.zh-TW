---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830069"
---
# <a name="assertphase-operation"></a><span data-ttu-id="a4153-102">AssertPhase 操作</span><span class="sxs-lookup"><span data-stu-id="a4153-102">AssertPhase operation</span></span>

<span data-ttu-id="a4153-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a4153-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a4153-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4153-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4153-105">判斷提示等於迭加狀態的階段具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="a4153-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="a4153-106">描述</span><span class="sxs-lookup"><span data-stu-id="a4153-106">Description</span></span>

<span data-ttu-id="a4153-107">這項作業會判斷出某些任意實數 $t $ 具有預期值的量子狀態的階段 $ \phi $，可能表示為 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1}) $。</span><span class="sxs-lookup"><span data-stu-id="a4153-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="a4153-108">輸入</span><span class="sxs-lookup"><span data-stu-id="a4153-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="a4153-109">預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a4153-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a4153-110">$ \Phi \in (-\pi，\pi] $ 的預期值。</span><span class="sxs-lookup"><span data-stu-id="a4153-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="a4153-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a4153-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a4153-112">儲存預期狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="a4153-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a4153-113">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a4153-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a4153-114">實際和預期之間差異的絕對容錯。</span><span class="sxs-lookup"><span data-stu-id="a4153-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4153-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4153-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="a4153-116">範例</span><span class="sxs-lookup"><span data-stu-id="a4153-116">Example</span></span>

<span data-ttu-id="a4153-117">下列判斷提示成功：處於 `qubit` state $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ ket {0} + e ^ {i 0.5} \ sqrt {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="a4153-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="a4153-118">`qubit` 處於 state $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ ket {0} + e ^ {-i 0.5} \ sqrt {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="a4153-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="a4153-119">`qubit` 處於 state $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ ket {0} + e ^ {i 0.2} \ sqrt {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="a4153-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`