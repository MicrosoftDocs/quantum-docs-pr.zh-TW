---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216654"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="72256-102">ControlledOnBitString 函式</span><span class="sxs-lookup"><span data-stu-id="72256-102">ControlledOnBitString function</span></span>

<span data-ttu-id="72256-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72256-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72256-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72256-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72256-105">傳回在目標暫存器上套用 oracle 的單一作業（如果控制項暫存器狀態對應到指定的位元遮罩）。</span><span class="sxs-lookup"><span data-stu-id="72256-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="72256-106">描述</span><span class="sxs-lookup"><span data-stu-id="72256-106">Description</span></span>

<span data-ttu-id="72256-107">此函式的輸出是可由單一轉換 $U $ 表示的運算，例如 \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1} ) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{cases} \end{align}，其中 $V $ 是代表操作動作的單一轉換 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="72256-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="72256-108">輸入</span><span class="sxs-lookup"><span data-stu-id="72256-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="72256-109">位： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="72256-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="72256-110">用來控制指定之單一作業的位字串。</span><span class="sxs-lookup"><span data-stu-id="72256-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="72256-111">oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="72256-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="72256-112">要在目標注冊上套用的單一作業。</span><span class="sxs-lookup"><span data-stu-id="72256-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="72256-113">輸出： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，t) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="72256-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="72256-114">`oracle`當控制項暫存器狀態對應至位元遮罩時，會在目標暫存器上套用的單一作業 `bits` 。</span><span class="sxs-lookup"><span data-stu-id="72256-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="72256-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="72256-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72256-116">不要</span><span class="sxs-lookup"><span data-stu-id="72256-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="72256-117">備註</span><span class="sxs-lookup"><span data-stu-id="72256-117">Remarks</span></span>

<span data-ttu-id="72256-118">指定的模式 `bits` 可能會縮短 `controlRegister` ，在這種情況下，會忽略額外的控制項量子位， (也就是，不會在 $ \ket {0} $ 和 $ \ket {1} $) 上控制。</span><span class="sxs-lookup"><span data-stu-id="72256-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="72256-119">如果超過 `bits` `controlRegister` ，則會引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="72256-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="72256-120">指定布林值陣列 `bits` 和單一作業 `oracle` 之後，此函式的輸出就是執行下列步驟的作業：</span><span class="sxs-lookup"><span data-stu-id="72256-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="72256-121">將作業套用 `X` 至控制項暫存器（對應至的元素）的每個量子位 `false` `bits` ;</span><span class="sxs-lookup"><span data-stu-id="72256-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="72256-122">適用于 `Controlled oracle` 控制項和目標暫存器;</span><span class="sxs-lookup"><span data-stu-id="72256-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="72256-123">將作業套用 `X` 至控制項暫存器的每個量子位，以再次對應至的專案，以將控制項暫存器傳回 `false` `bits` 至原始狀態。</span><span class="sxs-lookup"><span data-stu-id="72256-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="72256-124">仿函數的輸出 `Controlled` 是的特殊案例， `ControlledOnBitString` 其中 `bits` 等於 `[true, ..., true]` 。</span><span class="sxs-lookup"><span data-stu-id="72256-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>