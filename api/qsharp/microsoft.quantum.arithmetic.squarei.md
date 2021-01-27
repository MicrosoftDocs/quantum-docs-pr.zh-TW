---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 6813c8144b0ac98bae404b5e9b97e08b06c6bb3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846303"
---
# <a name="squarei-operation"></a><span data-ttu-id="d28bc-102">SquareI 操作</span><span class="sxs-lookup"><span data-stu-id="d28bc-102">SquareI operation</span></span>

<span data-ttu-id="d28bc-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d28bc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d28bc-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d28bc-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d28bc-105">將整數的平方計算 `xs` 為 `result` ，一開始必須為零。</span><span class="sxs-lookup"><span data-stu-id="d28bc-105">Computes the square of the integer `xs` into `result`, which must be zero initially.</span></span>

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d28bc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d28bc-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d28bc-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d28bc-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d28bc-108">$n $ 位數位到平方 (LittleEndian) </span><span class="sxs-lookup"><span data-stu-id="d28bc-108">$n$-bit number to square (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="d28bc-109">結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d28bc-109">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d28bc-110">$ 2n $ bit result (LittleEndian) ，必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="d28bc-110">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d28bc-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d28bc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d28bc-112">備註</span><span class="sxs-lookup"><span data-stu-id="d28bc-112">Remarks</span></span>

<span data-ttu-id="d28bc-113">使用標準的 shift 和 add 方法來計算方形。</span><span class="sxs-lookup"><span data-stu-id="d28bc-113">Uses a standard shift-and-add approach to compute the square.</span></span> <span data-ttu-id="d28bc-114">相較于在套用一般乘數然後復原複製作業之前，會先複製 xs 的正向解決方案，節省 $n-$1 量子位。</span><span class="sxs-lookup"><span data-stu-id="d28bc-114">Saves $n-1$ qubits compared to the straight-forward solution which first copies out xs before applying a regular multiplier and then undoing the copy operation.</span></span>