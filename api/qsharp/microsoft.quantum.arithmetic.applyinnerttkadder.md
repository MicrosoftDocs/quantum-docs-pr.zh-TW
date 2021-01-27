---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: c822933340d592061eb039af7c6e438212abc265
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843822"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="fe699-102">ApplyInnerTTKAdder 操作</span><span class="sxs-lookup"><span data-stu-id="fe699-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="fe699-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fe699-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fe699-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe699-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe699-105">執行作業 RippleCarryAdderTTK 的內部加法函數。</span><span class="sxs-lookup"><span data-stu-id="fe699-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="fe699-106">這是使用外部作業 conjugated 的內部作業，用來建立完整的加入程式。</span><span class="sxs-lookup"><span data-stu-id="fe699-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fe699-107">輸入</span><span class="sxs-lookup"><span data-stu-id="fe699-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="fe699-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fe699-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fe699-109">LittleEndian 量子位將第一個整數被加數輸入編碼為 RippleCarryAdderTTK。</span><span class="sxs-lookup"><span data-stu-id="fe699-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="fe699-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fe699-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fe699-111">LittleEndian 量子位將第二個整數被加數輸入編碼為 RippleCarryAdderTTK。</span><span class="sxs-lookup"><span data-stu-id="fe699-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="fe699-112">攜帶： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fe699-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fe699-113">帶有量子位，是以總和的最高有效位進行 xor。</span><span class="sxs-lookup"><span data-stu-id="fe699-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe699-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe699-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fe699-115">備註</span><span class="sxs-lookup"><span data-stu-id="fe699-115">Remarks</span></span>

<span data-ttu-id="fe699-116">指定的受控制作業會使用作業的對稱和相互取消，以改善將控制項加入至每個作業的預設執行。</span><span class="sxs-lookup"><span data-stu-id="fe699-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="fe699-117">參考資料</span><span class="sxs-lookup"><span data-stu-id="fe699-117">References</span></span>

- <span data-ttu-id="fe699-118">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro：「量子加法線路和未系結的展開」、量子資訊和計算、2010。</span><span class="sxs-lookup"><span data-stu-id="fe699-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530