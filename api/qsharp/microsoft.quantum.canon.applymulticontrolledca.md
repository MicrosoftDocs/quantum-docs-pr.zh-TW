---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209276"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="9d4b4-102">ApplyMultiControlledCA 操作</span><span class="sxs-lookup"><span data-stu-id="9d4b4-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="9d4b4-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d4b4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d4b4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d4b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d4b4-105">套用單一受控制作業的乘法受控制版本。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="9d4b4-106">修飾詞 `CA` 表示單一量子位作業是可控制且 adjointable 的。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9d4b4-107">輸入</span><span class="sxs-lookup"><span data-stu-id="9d4b4-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="9d4b4-108">singlyControlledOp： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="9d4b4-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9d4b4-109">在單一量子位上控制的操作。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="9d4b4-110">作業引數中的第一個量子位假設是一個控制項，而其餘的則假設為目標量子位。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="9d4b4-111">`ApplyMultiControlled` 一律會呼叫長度至少為 `singlyControlledOp` 1 的引數。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="9d4b4-112">ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="9d4b4-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="9d4b4-113">要用於此結構的受控制控制項-NOT 閘道。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="9d4b4-114">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9d4b4-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9d4b4-115">`singlyControlledOp`要控制的量子位。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="9d4b4-116">的長度 `controls` 必須至少為1。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="9d4b4-117">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9d4b4-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9d4b4-118">作用的目標量子位 `singlyControlledOp` 。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d4b4-119">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d4b4-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9d4b4-120">備註</span><span class="sxs-lookup"><span data-stu-id="9d4b4-120">Remarks</span></span>

<span data-ttu-id="9d4b4-121">這種作業只會使用 clean ancilla 量子位。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="9d4b4-122">如需說明和電路圖表，請參閱 Nielsen & Chuang 中的圖4.10，第4.3 節。</span><span class="sxs-lookup"><span data-stu-id="9d4b4-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="9d4b4-123">參考</span><span class="sxs-lookup"><span data-stu-id="9d4b4-123">References</span></span>

- [<span data-ttu-id="9d4b4-124">*Michael Nielsen、Isaac Chuang*、量子計算和量子資訊</span><span class="sxs-lookup"><span data-stu-id="9d4b4-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="9d4b4-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9d4b4-125">See Also</span></span>

- [<span data-ttu-id="9d4b4-126">Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="9d4b4-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)