---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700014"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="310eb-102">ApplyOuterTTKAdder 操作</span><span class="sxs-lookup"><span data-stu-id="310eb-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="310eb-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="310eb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="310eb-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="310eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="310eb-105">將 RippleCarryAdderTTK 的外部作業實作為內部作業，以建立完整的對應程式。</span><span class="sxs-lookup"><span data-stu-id="310eb-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="310eb-106">輸入</span><span class="sxs-lookup"><span data-stu-id="310eb-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="310eb-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="310eb-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="310eb-108">LittleEndian 量子位將第一個整數被加數輸入編碼為 RippleCarryAdderTTK。</span><span class="sxs-lookup"><span data-stu-id="310eb-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="310eb-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="310eb-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="310eb-110">LittleEndian 量子位將第二個整數被加數輸入編碼為 RippleCarryAdderTTK。</span><span class="sxs-lookup"><span data-stu-id="310eb-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="310eb-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="310eb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="310eb-112">參考</span><span class="sxs-lookup"><span data-stu-id="310eb-112">References</span></span>

- <span data-ttu-id="310eb-113">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro：「量子加法線路和未系結的展開」、量子資訊和計算、2010。</span><span class="sxs-lookup"><span data-stu-id="310eb-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530