---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700059"
---
# <a name="addfxp-operation"></a><span data-ttu-id="5047b-102">AddFxP 操作</span><span class="sxs-lookup"><span data-stu-id="5047b-102">AddFxP operation</span></span>

<span data-ttu-id="5047b-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5047b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5047b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5047b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5047b-105">新增儲存在量子暫存器中的兩個固定點數位。</span><span class="sxs-lookup"><span data-stu-id="5047b-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a><span data-ttu-id="5047b-106">描述</span><span class="sxs-lookup"><span data-stu-id="5047b-106">Description</span></span>

<span data-ttu-id="5047b-107">假設有兩個固定點暫存器分別在狀態 $ \ket{f_1} $ 和 $ \ket{f_2} $ 中，則執行作業 $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $。</span><span class="sxs-lookup"><span data-stu-id="5047b-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="5047b-108">輸入</span><span class="sxs-lookup"><span data-stu-id="5047b-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="5047b-109">fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5047b-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5047b-110">第一個固定點數位</span><span class="sxs-lookup"><span data-stu-id="5047b-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="5047b-111">fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5047b-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5047b-112">第二個固定點數位將會更新，以包含兩個輸入的總和。</span><span class="sxs-lookup"><span data-stu-id="5047b-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5047b-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5047b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5047b-114">備註</span><span class="sxs-lookup"><span data-stu-id="5047b-114">Remarks</span></span>

<span data-ttu-id="5047b-115">目前的執行需要有兩個固定點數位，使其具有與最小有效位的相同點位置計數，亦即 $n _i $ 和 $p _i $ 必須相等。</span><span class="sxs-lookup"><span data-stu-id="5047b-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>