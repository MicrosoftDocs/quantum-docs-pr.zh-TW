---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697966"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="7de84-102">InjectPi4YRotation 操作</span><span class="sxs-lookup"><span data-stu-id="7de84-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="7de84-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7de84-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7de84-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7de84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7de84-105">旋轉 Y 軸上的單一量子位與π/4。</span><span class="sxs-lookup"><span data-stu-id="7de84-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="7de84-106">描述</span><span class="sxs-lookup"><span data-stu-id="7de84-106">Description</span></span>

<span data-ttu-id="7de84-107">執行有關的π/4 旋轉 `Y` 。</span><span class="sxs-lookup"><span data-stu-id="7de84-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="7de84-108">旋轉是藉由使用魔術狀態來執行;也就是狀態 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket 的複本 {8} {1} 。</span><span class="sxs-lookup"><span data-stu-id="7de84-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="7de84-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7de84-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="7de84-110">輸入</span><span class="sxs-lookup"><span data-stu-id="7de84-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="7de84-111">資料： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7de84-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7de84-112">要 $Y $ \pi/$4 旋轉的量子位。</span><span class="sxs-lookup"><span data-stu-id="7de84-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="7de84-113">魔術： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7de84-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7de84-114">一開始是魔術狀態的量子位。</span><span class="sxs-lookup"><span data-stu-id="7de84-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="7de84-115">這項作業的下列應用程式 `magic` 會傳回 $ \ket {0} $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="7de84-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7de84-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7de84-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7de84-117">備註</span><span class="sxs-lookup"><span data-stu-id="7de84-117">Remarks</span></span>

<span data-ttu-id="7de84-118">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="7de84-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="7de84-119">及</span><span class="sxs-lookup"><span data-stu-id="7de84-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="7de84-120">這項作業支援 `Adjoint` 仿函數，在此情況下會使用相同的魔術狀態，但對資料量子位的影響是 $-\ pi/4 $ $Y $-旋轉。</span><span class="sxs-lookup"><span data-stu-id="7de84-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>