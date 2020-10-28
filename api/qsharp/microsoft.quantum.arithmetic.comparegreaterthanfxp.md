---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699926"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="ba603-102">CompareGreaterThanFxP 操作</span><span class="sxs-lookup"><span data-stu-id="ba603-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="ba603-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ba603-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ba603-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba603-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba603-105">比較儲存在量子暫存器中的兩個固定點數位，並控制結果的翻轉。</span><span class="sxs-lookup"><span data-stu-id="ba603-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ba603-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ba603-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="ba603-107">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ba603-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ba603-108">要比較的第一個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="ba603-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="ba603-109">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ba603-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ba603-110">要比較的第二個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="ba603-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="ba603-111">結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ba603-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ba603-112">比較的結果。</span><span class="sxs-lookup"><span data-stu-id="ba603-112">Result of the comparison.</span></span> <span data-ttu-id="ba603-113">如果為，則會翻轉 `fp1 > fp2` 。</span><span class="sxs-lookup"><span data-stu-id="ba603-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ba603-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ba603-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ba603-115">備註</span><span class="sxs-lookup"><span data-stu-id="ba603-115">Remarks</span></span>

<span data-ttu-id="ba603-116">目前的執行需要兩個固定點數位具有相同的點位置和相同的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="ba603-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>