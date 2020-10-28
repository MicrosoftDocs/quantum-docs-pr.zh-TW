---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699357"
---
# <a name="andladder-operation"></a><span data-ttu-id="59a97-102">AndLadder 操作</span><span class="sxs-lookup"><span data-stu-id="59a97-102">AndLadder operation</span></span>

<span data-ttu-id="59a97-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59a97-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59a97-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59a97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59a97-105">在目標量子位的註冊上執行受控制的「和階梯」。</span><span class="sxs-lookup"><span data-stu-id="59a97-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="59a97-106">描述</span><span class="sxs-lookup"><span data-stu-id="59a97-106">Description</span></span>

<span data-ttu-id="59a97-107">這項作業會套用依下列計算方式對應的轉換：計算基礎： $ $ \begin{align} \ket{x \_ 1、\dots ..、x \_ n} \ket{y \_ 1、\dots ..、y \_ {n-1}} \mapsto \ket{x \_ 1、\dots ..、x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2) \dots ..、y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}、\end{align} $ $，其中 $ \ket{x \_ 1、\dots ..、x \_ n} $ 指的是的計算基礎狀態 `controls` ，其中 $ \ket{y \_ 1、\dots ..、y \_ {n-1}} $ 指的是的計算基礎狀態 `targets` 。</span><span class="sxs-lookup"><span data-stu-id="59a97-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="59a97-108">輸入</span><span class="sxs-lookup"><span data-stu-id="59a97-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="59a97-109">ccnot： [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="59a97-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="59a97-110">要用於結構的 CCNOT 閘道。</span><span class="sxs-lookup"><span data-stu-id="59a97-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="59a97-111">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="59a97-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="59a97-112">要當做和階梯控制項使用的量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="59a97-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="59a97-113">這項作業會保留非變異的計算基礎狀態 `controls` 。</span><span class="sxs-lookup"><span data-stu-id="59a97-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="59a97-114">的長度 `controls` 必須至少為2，而且必須等於1加上的長度 `targets` 。</span><span class="sxs-lookup"><span data-stu-id="59a97-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="59a97-115">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="59a97-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="59a97-116">的長度 `targets` 必須至少為1，且長度必須等於 `controls` 減號一。</span><span class="sxs-lookup"><span data-stu-id="59a97-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59a97-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59a97-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="59a97-118">備註</span><span class="sxs-lookup"><span data-stu-id="59a97-118">Remarks</span></span>

- <span data-ttu-id="59a97-119">當做和的一部分使用 <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> 。</span><span class="sxs-lookup"><span data-stu-id="59a97-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="59a97-120">如需說明和電路圖表，請參閱 Nielsen & Chuang 中的圖4.10，第4.3 節。</span><span class="sxs-lookup"><span data-stu-id="59a97-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="59a97-121">參考</span><span class="sxs-lookup"><span data-stu-id="59a97-121">References</span></span>

- [<span data-ttu-id="59a97-122">*Michael Nielsen、Isaac Chuang* 、量子計算和量子資訊</span><span class="sxs-lookup"><span data-stu-id="59a97-122"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)