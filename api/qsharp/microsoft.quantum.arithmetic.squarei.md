---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699533"
---
# <a name="squarei-operation"></a><span data-ttu-id="ec1a7-102">SquareI 操作</span><span class="sxs-lookup"><span data-stu-id="ec1a7-102">SquareI operation</span></span>

<span data-ttu-id="ec1a7-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ec1a7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ec1a7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec1a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec1a7-105">將整數的平方計算 `xs` 為 `result` ，一開始必須為零。</span><span class="sxs-lookup"><span data-stu-id="ec1a7-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ec1a7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ec1a7-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ec1a7-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ec1a7-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ec1a7-108">$n $ 位數位到平方 (LittleEndian) </span><span class="sxs-lookup"><span data-stu-id="ec1a7-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="ec1a7-109">結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ec1a7-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ec1a7-110">$ 2n $ bit result (LittleEndian) ，必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="ec1a7-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec1a7-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec1a7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ec1a7-112">備註</span><span class="sxs-lookup"><span data-stu-id="ec1a7-112">Remarks</span></span>

<span data-ttu-id="ec1a7-113">使用標準的 shift 和 add 方法來計算方形。</span><span class="sxs-lookup"><span data-stu-id="ec1a7-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="ec1a7-114">相較于在套用一般乘數然後復原複製作業之前，會先複製 xs 的正向解決方案，節省 $n-$1 量子位。</span><span class="sxs-lookup"><span data-stu-id="ec1a7-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>