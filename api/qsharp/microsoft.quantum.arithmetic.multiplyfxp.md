---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699573"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="9a3f0-102">MultiplyFxP 操作</span><span class="sxs-lookup"><span data-stu-id="9a3f0-102">MultiplyFxP operation</span></span>

<span data-ttu-id="9a3f0-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9a3f0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9a3f0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a3f0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a3f0-105">將量子暫存器中的兩個固定點數位相乘。</span><span class="sxs-lookup"><span data-stu-id="9a3f0-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="9a3f0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9a3f0-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="9a3f0-107">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9a3f0-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9a3f0-108">第一個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="9a3f0-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="9a3f0-109">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9a3f0-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9a3f0-110">第二個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="9a3f0-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="9a3f0-111">結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9a3f0-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9a3f0-112">結果固定點數必須一開始就是狀態 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="9a3f0-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a3f0-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a3f0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9a3f0-114">備註</span><span class="sxs-lookup"><span data-stu-id="9a3f0-114">Remarks</span></span>

<span data-ttu-id="9a3f0-115">目前的執行需要三個固定點數位具有相同的點位置和相同的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="9a3f0-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>