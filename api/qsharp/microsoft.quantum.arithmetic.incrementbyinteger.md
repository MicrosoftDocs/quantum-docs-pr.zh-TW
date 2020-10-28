---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699863"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="5e010-102">IncrementByInteger 操作</span><span class="sxs-lookup"><span data-stu-id="5e010-102">IncrementByInteger operation</span></span>

<span data-ttu-id="5e010-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5e010-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5e010-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e010-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e010-105">使用階段旋轉，以傳統整數遞增未簽署的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="5e010-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="5e010-106">描述</span><span class="sxs-lookup"><span data-stu-id="5e010-106">Description</span></span>

<span data-ttu-id="5e010-107">假設將 `target` 不帶正負號的整數編碼 $x $ 以位元組由小到大的編碼方式，且 `increment` 等於 $a $。</span><span class="sxs-lookup"><span data-stu-id="5e010-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="5e010-108">然後，這項作業會執行單一 $ \ket{x} \mapsto \ket{x + a} $，其中加法會執行模數 $ 2 ^ n $，其中 $n = \texttt{Length (target！ ) } $。</span><span class="sxs-lookup"><span data-stu-id="5e010-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="5e010-109">輸入</span><span class="sxs-lookup"><span data-stu-id="5e010-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="5e010-110">遞增： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e010-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e010-111">用來遞增的整數 `target` 。</span><span class="sxs-lookup"><span data-stu-id="5e010-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="5e010-112">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e010-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5e010-113">量子暫存器使用位元組由小到大編碼來編碼不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="5e010-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e010-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e010-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

