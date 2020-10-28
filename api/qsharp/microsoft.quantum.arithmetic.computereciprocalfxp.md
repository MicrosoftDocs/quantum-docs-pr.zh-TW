---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699910"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="9c509-102">ComputeReciprocalFxP 操作</span><span class="sxs-lookup"><span data-stu-id="9c509-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="9c509-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9c509-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9c509-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c509-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c509-105">計算固定點數位 $x $ 的 $ 1/x $。</span><span class="sxs-lookup"><span data-stu-id="9c509-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="9c509-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9c509-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="9c509-107">x： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9c509-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9c509-108">要反轉的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="9c509-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="9c509-109">結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9c509-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9c509-110">將保留結果的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="9c509-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="9c509-111">必須初始化為 $ \ket{0.0} $。</span><span class="sxs-lookup"><span data-stu-id="9c509-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c509-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c509-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

