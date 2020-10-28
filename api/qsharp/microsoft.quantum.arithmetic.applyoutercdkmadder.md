---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700015"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="df61b-102">ApplyOuterCDKMAdder 操作</span><span class="sxs-lookup"><span data-stu-id="df61b-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="df61b-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="df61b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="df61b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df61b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df61b-105">可回復的就地 ripple，包含在下面的整數加法運算 RippleCarryAdderCDKM 中使用的作業。</span><span class="sxs-lookup"><span data-stu-id="df61b-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="df61b-106">假設有兩個量子位暫存器 `xs` 和 `ys` 相同的長度，則作業會將 ripple 套用至 CNOT 和 CCNOT 閘道的順序，並以中的量子位作為 `xs` `ys` 控制項和量子位 `xs` 做為目標。</span><span class="sxs-lookup"><span data-stu-id="df61b-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="df61b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="df61b-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="df61b-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="df61b-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="df61b-109">第一個量子位註冊，包含控制項和目標。</span><span class="sxs-lookup"><span data-stu-id="df61b-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="df61b-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="df61b-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="df61b-111">第二個量子位註冊，參與控制項。</span><span class="sxs-lookup"><span data-stu-id="df61b-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="df61b-112">ancilla： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="df61b-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="df61b-113">在 RippleCarryAdderCDKM 中使用的 ancilla 量子位會傳遞至這項作業。</span><span class="sxs-lookup"><span data-stu-id="df61b-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df61b-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df61b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="df61b-115">參考</span><span class="sxs-lookup"><span data-stu-id="df61b-115">References</span></span>

- <span data-ttu-id="df61b-116">Steven Cuccaro、Thomas g. Draper、Samuel A. Kutin、David Petrie Moulton：「新的量子 ripple-攜帶加法電路」、2004。</span><span class="sxs-lookup"><span data-stu-id="df61b-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1