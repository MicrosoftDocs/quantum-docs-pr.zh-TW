---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 4ff0abe67a6d18204e417a45f8d8f1d092d02b88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200793"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="c0f0c-102">InjectPi4YRotation 操作</span><span class="sxs-lookup"><span data-stu-id="c0f0c-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="c0f0c-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c0f0c-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c0f0c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0f0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0f0c-105">旋轉 Y 軸上的單一量子位與π/4。</span><span class="sxs-lookup"><span data-stu-id="c0f0c-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="c0f0c-106">描述</span><span class="sxs-lookup"><span data-stu-id="c0f0c-106">Description</span></span>

<span data-ttu-id="c0f0c-107">執行有關的π/4 旋轉 `Y` 。</span><span class="sxs-lookup"><span data-stu-id="c0f0c-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="c0f0c-108">旋轉是藉由使用魔術狀態來執行;也就是狀態 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket 的複本 {8} {1} 。</span><span class="sxs-lookup"><span data-stu-id="c0f0c-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="c0f0c-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="c0f0c-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="c0f0c-110">輸入</span><span class="sxs-lookup"><span data-stu-id="c0f0c-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="c0f0c-111">資料： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c0f0c-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c0f0c-112">要 $Y $ \pi/$4 旋轉的量子位。</span><span class="sxs-lookup"><span data-stu-id="c0f0c-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="c0f0c-113">魔術： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c0f0c-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c0f0c-114">一開始是魔術狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="c0f0c-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="c0f0c-115">這項作業的下列應用程式 `magic` 會傳回 $ \ket {0} $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="c0f0c-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0f0c-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0f0c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c0f0c-117">備註</span><span class="sxs-lookup"><span data-stu-id="c0f0c-117">Remarks</span></span>

<span data-ttu-id="c0f0c-118">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="c0f0c-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="c0f0c-119">及</span><span class="sxs-lookup"><span data-stu-id="c0f0c-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="c0f0c-120">這項作業支援 `Adjoint` 仿函數，在此情況下會使用相同的魔術狀態，但對資料量子位的影響是 $-\ pi/4 $ $Y $-旋轉。</span><span class="sxs-lookup"><span data-stu-id="c0f0c-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>