---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219068"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="85b5e-102">ApplyControlledOnBitString 操作</span><span class="sxs-lookup"><span data-stu-id="85b5e-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="85b5e-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="85b5e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="85b5e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85b5e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85b5e-105">在目標暫存器上套用單一作業，該作業是由指定之位遮罩所指定的狀態所控制。</span><span class="sxs-lookup"><span data-stu-id="85b5e-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="85b5e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="85b5e-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="85b5e-107">位： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="85b5e-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="85b5e-108">用來控制指定之單一作業的位字串。</span><span class="sxs-lookup"><span data-stu-id="85b5e-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="85b5e-109">oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="85b5e-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="85b5e-110">要在目標注冊上套用的單一作業。</span><span class="sxs-lookup"><span data-stu-id="85b5e-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="85b5e-111">controlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85b5e-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="85b5e-112">控制應用程式的量子暫存器 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="85b5e-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="85b5e-113">targetRegister： t</span><span class="sxs-lookup"><span data-stu-id="85b5e-113">targetRegister : 'T</span></span>

<span data-ttu-id="85b5e-114">要傳遞至做為輸入的目標暫存器 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="85b5e-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="85b5e-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85b5e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="85b5e-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="85b5e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85b5e-117">不要</span><span class="sxs-lookup"><span data-stu-id="85b5e-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="85b5e-118">備註</span><span class="sxs-lookup"><span data-stu-id="85b5e-118">Remarks</span></span>

<span data-ttu-id="85b5e-119">指定的模式 `bits` 可能會縮短 `controlRegister` ，在這種情況下，會忽略額外的控制項量子位， (也就是，不會在 $ \ket {0} $ 和 $ \ket {1} $) 上控制。</span><span class="sxs-lookup"><span data-stu-id="85b5e-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="85b5e-120">如果超過 `bits` `controlRegister` ，則會引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="85b5e-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="85b5e-121">例如， `bits = [0,1,0,0,1]` 表示 `oracle` 只有當 `controlRegister` 位於 state $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $ 時，才適用。</span><span class="sxs-lookup"><span data-stu-id="85b5e-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>