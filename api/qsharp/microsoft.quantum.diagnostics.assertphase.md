---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698146"
---
# <a name="assertphase-operation"></a><span data-ttu-id="76f8d-102">AssertPhase 操作</span><span class="sxs-lookup"><span data-stu-id="76f8d-102">AssertPhase operation</span></span>

<span data-ttu-id="76f8d-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="76f8d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="76f8d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76f8d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76f8d-105">判斷提示等於迭加狀態的階段具有預期的值。</span><span class="sxs-lookup"><span data-stu-id="76f8d-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="76f8d-106">描述</span><span class="sxs-lookup"><span data-stu-id="76f8d-106">Description</span></span>

<span data-ttu-id="76f8d-107">這項作業會判斷出某些任意實數 $t $ 具有預期值的量子狀態的階段 $ \phi $，可能表示為 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket {1}) $。</span><span class="sxs-lookup"><span data-stu-id="76f8d-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="76f8d-108">輸入</span><span class="sxs-lookup"><span data-stu-id="76f8d-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="76f8d-109">預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="76f8d-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="76f8d-110">$ \Phi \in (-\pi，\pi] $ 的預期值。</span><span class="sxs-lookup"><span data-stu-id="76f8d-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="76f8d-111">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="76f8d-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="76f8d-112">儲存預期狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="76f8d-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="76f8d-113">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="76f8d-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="76f8d-114">實際和預期之間差異的絕對容錯。</span><span class="sxs-lookup"><span data-stu-id="76f8d-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76f8d-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76f8d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

