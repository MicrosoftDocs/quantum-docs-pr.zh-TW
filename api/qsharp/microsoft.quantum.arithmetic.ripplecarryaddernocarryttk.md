---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: a539d85a4800c2f4452a1c6fe2c4f88a6296c3e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221992"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="7c74d-102">RippleCarryAdderNoCarryTTK 操作</span><span class="sxs-lookup"><span data-stu-id="7c74d-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="7c74d-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7c74d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7c74d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c74d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c74d-105">可反轉的就地 ripple-在不執行的情況下，加入兩個整數。</span><span class="sxs-lookup"><span data-stu-id="7c74d-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7c74d-106">描述</span><span class="sxs-lookup"><span data-stu-id="7c74d-106">Description</span></span>

<span data-ttu-id="7c74d-107">假設有兩個 $n $ bit 整數編碼于 LittleEndian 暫存器 `xs` 和中 `ys` ，則作業會計算兩個整數模數 $ 2 ^ n $ 的總和，其中 $n $ 是輸入和的位大小 `xs` `ys` 。</span><span class="sxs-lookup"><span data-stu-id="7c74d-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="7c74d-108">它不會計算執行時位。</span><span class="sxs-lookup"><span data-stu-id="7c74d-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="7c74d-109">輸入</span><span class="sxs-lookup"><span data-stu-id="7c74d-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7c74d-110">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c74d-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c74d-111">LittleEndian 量子位登錄第一個整數被加數的編碼。</span><span class="sxs-lookup"><span data-stu-id="7c74d-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="7c74d-112">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7c74d-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7c74d-113">LittleEndian 量子位暫存器第二個整數被加數的編碼，會修改成保存總和的 $n $ 最不重要的位。</span><span class="sxs-lookup"><span data-stu-id="7c74d-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c74d-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c74d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7c74d-115">備註</span><span class="sxs-lookup"><span data-stu-id="7c74d-115">Remarks</span></span>

<span data-ttu-id="7c74d-116">這種作業具有與 RippleCarryAdderTTK 相同的功能，但不會傳回執行位。</span><span class="sxs-lookup"><span data-stu-id="7c74d-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="7c74d-117">參考</span><span class="sxs-lookup"><span data-stu-id="7c74d-117">References</span></span>

- <span data-ttu-id="7c74d-118">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro：「量子加法線路和未系結的展開」、量子資訊和計算、2010。</span><span class="sxs-lookup"><span data-stu-id="7c74d-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530