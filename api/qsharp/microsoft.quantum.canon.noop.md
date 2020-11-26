---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205961"
---
# <a name="noop-operation"></a><span data-ttu-id="19232-102">NoOp 操作</span><span class="sxs-lookup"><span data-stu-id="19232-102">NoOp operation</span></span>

<span data-ttu-id="19232-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="19232-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="19232-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="19232-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="19232-105">在引數上 (非 op) 執行身分識別作業。</span><span class="sxs-lookup"><span data-stu-id="19232-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="19232-106">描述</span><span class="sxs-lookup"><span data-stu-id="19232-106">Description</span></span>

<span data-ttu-id="19232-107">這項作業會接受任何類型的值，而且不會對它執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="19232-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="19232-108">只要預期的是作業類型的輸入，但不應該採取任何動作，這項功能就很有用。</span><span class="sxs-lookup"><span data-stu-id="19232-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="19232-109">比方說，如果特定錯誤更正問題指出未發生任何錯誤， `NoOp<Qubit[]>` 則可能是正確的修復程式。</span><span class="sxs-lookup"><span data-stu-id="19232-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="19232-110">同樣地，如果作業預期狀態準備程式做為輸入， `NoOp<Qubit[]>` 就可以用來準備狀態 $ \ket{0 \cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="19232-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="19232-111">輸入</span><span class="sxs-lookup"><span data-stu-id="19232-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="19232-112">輸入： t</span><span class="sxs-lookup"><span data-stu-id="19232-112">input : 'T</span></span>

<span data-ttu-id="19232-113">要忽略的值。</span><span class="sxs-lookup"><span data-stu-id="19232-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="19232-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="19232-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="19232-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="19232-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="19232-116">不要</span><span class="sxs-lookup"><span data-stu-id="19232-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="19232-117">備註</span><span class="sxs-lookup"><span data-stu-id="19232-117">Remarks</span></span>

<span data-ttu-id="19232-118">在幾乎所有情況下，必須明確指定的型別參數 `NoOp` 。</span><span class="sxs-lookup"><span data-stu-id="19232-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="19232-119">例如，與 `NoOp<Qubit>` 相同 <xref:microsoft.quantum.intrinsic.i> 。</span><span class="sxs-lookup"><span data-stu-id="19232-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="19232-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="19232-120">See Also</span></span>

- [<span data-ttu-id="19232-121">... I</span><span class="sxs-lookup"><span data-stu-id="19232-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)