---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700046"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="640c0-102">ApplyInnerTTKAdder 操作</span><span class="sxs-lookup"><span data-stu-id="640c0-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="640c0-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="640c0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="640c0-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="640c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="640c0-105">執行作業 RippleCarryAdderTTK 的內部加法函數。</span><span class="sxs-lookup"><span data-stu-id="640c0-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="640c0-106">這是使用外部作業 conjugated 的內部作業，用來建立完整的加入程式。</span><span class="sxs-lookup"><span data-stu-id="640c0-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="640c0-107">輸入</span><span class="sxs-lookup"><span data-stu-id="640c0-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="640c0-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="640c0-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="640c0-109">LittleEndian 量子位將第一個整數被加數輸入編碼為 RippleCarryAdderTTK。</span><span class="sxs-lookup"><span data-stu-id="640c0-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="640c0-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="640c0-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="640c0-111">LittleEndian 量子位將第二個整數被加數輸入編碼為 RippleCarryAdderTTK。</span><span class="sxs-lookup"><span data-stu-id="640c0-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="640c0-112">攜帶： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="640c0-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="640c0-113">帶有量子位，是以總和的最高有效位進行 xor。</span><span class="sxs-lookup"><span data-stu-id="640c0-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="640c0-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="640c0-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="640c0-115">備註</span><span class="sxs-lookup"><span data-stu-id="640c0-115">Remarks</span></span>

<span data-ttu-id="640c0-116">指定的受控制作業會使用作業的對稱和相互取消，以改善將控制項加入至每個作業的預設執行。</span><span class="sxs-lookup"><span data-stu-id="640c0-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="640c0-117">參考</span><span class="sxs-lookup"><span data-stu-id="640c0-117">References</span></span>

- <span data-ttu-id="640c0-118">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro：「量子加法線路和未系結的展開」、量子資訊和計算、2010。</span><span class="sxs-lookup"><span data-stu-id="640c0-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530