---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843041"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="a2c19-102">MultiplyFxP 操作</span><span class="sxs-lookup"><span data-stu-id="a2c19-102">MultiplyFxP operation</span></span>

<span data-ttu-id="a2c19-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a2c19-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a2c19-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a2c19-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a2c19-105">將量子暫存器中的兩個固定點數位相乘。</span><span class="sxs-lookup"><span data-stu-id="a2c19-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a2c19-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a2c19-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="a2c19-107">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a2c19-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a2c19-108">第一個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="a2c19-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="a2c19-109">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a2c19-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a2c19-110">第二個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="a2c19-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="a2c19-111">結果： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a2c19-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a2c19-112">結果固定點數必須一開始就是狀態 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="a2c19-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2c19-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2c19-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a2c19-114">備註</span><span class="sxs-lookup"><span data-stu-id="a2c19-114">Remarks</span></span>

<span data-ttu-id="a2c19-115">目前的執行需要三個固定點數位具有相同的點位置和相同的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="a2c19-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>