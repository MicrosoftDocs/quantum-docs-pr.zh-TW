---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191035"
---
# <a name="addfxp-operation"></a><span data-ttu-id="9fa74-102">AddFxP 操作</span><span class="sxs-lookup"><span data-stu-id="9fa74-102">AddFxP operation</span></span>

<span data-ttu-id="9fa74-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9fa74-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9fa74-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9fa74-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9fa74-105">新增儲存在量子暫存器中的兩個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="9fa74-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9fa74-106">描述</span><span class="sxs-lookup"><span data-stu-id="9fa74-106">Description</span></span>

<span data-ttu-id="9fa74-107">假設有兩個固定點暫存器分別在狀態 $ \ket{f_1} $ 和 $ \ket{f_2} $ 中，則執行作業 $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $。</span><span class="sxs-lookup"><span data-stu-id="9fa74-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="9fa74-108">輸入</span><span class="sxs-lookup"><span data-stu-id="9fa74-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="9fa74-109">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9fa74-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9fa74-110">第一個固定點數位</span><span class="sxs-lookup"><span data-stu-id="9fa74-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="9fa74-111">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9fa74-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9fa74-112">第二個固定點數位將會更新，以包含兩個輸入的總和。</span><span class="sxs-lookup"><span data-stu-id="9fa74-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9fa74-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9fa74-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9fa74-114">備註</span><span class="sxs-lookup"><span data-stu-id="9fa74-114">Remarks</span></span>

<span data-ttu-id="9fa74-115">目前的執行需要有兩個固定點數位，使其具有與最小有效位的相同點位置計數，亦即 $n _i $ 和 $p _i $ 必須相等。</span><span class="sxs-lookup"><span data-stu-id="9fa74-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>