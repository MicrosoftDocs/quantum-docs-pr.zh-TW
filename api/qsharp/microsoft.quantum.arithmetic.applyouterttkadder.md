---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: aed15a4d1f3ca7121d6da665f5c08442fd495619
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190610"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="26b36-102">ApplyOuterTTKAdder 操作</span><span class="sxs-lookup"><span data-stu-id="26b36-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="26b36-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="26b36-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="26b36-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26b36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26b36-105">將 RippleCarryAdderTTK 的外部作業實作為內部作業，以建立完整的對應程式。</span><span class="sxs-lookup"><span data-stu-id="26b36-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="26b36-106">輸入</span><span class="sxs-lookup"><span data-stu-id="26b36-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="26b36-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="26b36-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="26b36-108">LittleEndian 量子位將第一個整數被加數輸入編碼為 RippleCarryAdderTTK。</span><span class="sxs-lookup"><span data-stu-id="26b36-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="26b36-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="26b36-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="26b36-110">LittleEndian 量子位將第二個整數被加數輸入編碼為 RippleCarryAdderTTK。</span><span class="sxs-lookup"><span data-stu-id="26b36-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26b36-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26b36-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="26b36-112">參考</span><span class="sxs-lookup"><span data-stu-id="26b36-112">References</span></span>

- <span data-ttu-id="26b36-113">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro：「量子加法線路和未系結的展開」、量子資訊和計算、2010。</span><span class="sxs-lookup"><span data-stu-id="26b36-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530