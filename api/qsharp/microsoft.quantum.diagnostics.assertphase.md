---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202255"
---
# <a name="assertphase-operation"></a><span data-ttu-id="397c8-102">AssertPhase 操作</span><span class="sxs-lookup"><span data-stu-id="397c8-102">AssertPhase operation</span></span>

<span data-ttu-id="397c8-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="397c8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="397c8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="397c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="397c8-105">判斷提示等於迭加狀態的階段具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="397c8-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="397c8-106">描述</span><span class="sxs-lookup"><span data-stu-id="397c8-106">Description</span></span>

<span data-ttu-id="397c8-107">這項作業會判斷出某些任意實數 $t $ 具有預期值的量子狀態的階段 $ \phi $，可能表示為 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1}) $。</span><span class="sxs-lookup"><span data-stu-id="397c8-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="397c8-108">輸入</span><span class="sxs-lookup"><span data-stu-id="397c8-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="397c8-109">預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="397c8-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="397c8-110">$ \Phi \in (-\pi，\pi] $ 的預期值。</span><span class="sxs-lookup"><span data-stu-id="397c8-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="397c8-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="397c8-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="397c8-112">儲存預期狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="397c8-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="397c8-113">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="397c8-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="397c8-114">實際和預期之間差異的絕對容錯。</span><span class="sxs-lookup"><span data-stu-id="397c8-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="397c8-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="397c8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

