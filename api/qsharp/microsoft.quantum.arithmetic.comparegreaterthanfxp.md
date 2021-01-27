---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843314"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="615f0-102">CompareGreaterThanFxP 操作</span><span class="sxs-lookup"><span data-stu-id="615f0-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="615f0-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="615f0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="615f0-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="615f0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="615f0-105">比較儲存在量子暫存器中的兩個固定點數位，並控制結果的翻轉。</span><span class="sxs-lookup"><span data-stu-id="615f0-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="615f0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="615f0-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="615f0-107">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="615f0-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="615f0-108">要比較的第一個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="615f0-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="615f0-109">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="615f0-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="615f0-110">要比較的第二個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="615f0-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="615f0-111">結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="615f0-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="615f0-112">比較的結果。</span><span class="sxs-lookup"><span data-stu-id="615f0-112">Result of the comparison.</span></span> <span data-ttu-id="615f0-113">如果為，則會翻轉 `fp1 > fp2` 。</span><span class="sxs-lookup"><span data-stu-id="615f0-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="615f0-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="615f0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="615f0-115">備註</span><span class="sxs-lookup"><span data-stu-id="615f0-115">Remarks</span></span>

<span data-ttu-id="615f0-116">目前的執行需要兩個固定點數位具有相同的點位置和相同的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="615f0-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>