---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3dd17e6bc913e84941a6b81f134e60536a4c4122
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219000"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="0e016-102">ApplyControlledOnInt 操作</span><span class="sxs-lookup"><span data-stu-id="0e016-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="0e016-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e016-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e016-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e016-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e016-105">如果控制項暫存器狀態對應到指定的正整數，則在目標暫存器上套用單一作業。</span><span class="sxs-lookup"><span data-stu-id="0e016-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0e016-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0e016-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="0e016-107">numberState： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0e016-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0e016-108">應控制作業的非負整數 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="0e016-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="0e016-109">oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0e016-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="0e016-110">要控制的單一作業。</span><span class="sxs-lookup"><span data-stu-id="0e016-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="0e016-111">controlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e016-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e016-112">控制應用程式的量子暫存器 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="0e016-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="0e016-113">targetRegister： t</span><span class="sxs-lookup"><span data-stu-id="0e016-113">targetRegister : 'T</span></span>

<span data-ttu-id="0e016-114">要套用的註冊 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="0e016-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e016-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e016-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0e016-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="0e016-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e016-117">不要</span><span class="sxs-lookup"><span data-stu-id="0e016-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="0e016-118">備註</span><span class="sxs-lookup"><span data-stu-id="0e016-118">Remarks</span></span>

<span data-ttu-id="0e016-119">的值 `numberState` 是使用位元組由大到小的編碼來解讀。</span><span class="sxs-lookup"><span data-stu-id="0e016-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="0e016-120">`numberState` 最多隻能有 $ 2 ^ \texttt{Length (controlRegister) }-$1。</span><span class="sxs-lookup"><span data-stu-id="0e016-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="0e016-121">例如， `numberState = 537` 表示 `oracle` 只有當 `controlRegister` 處於狀態 $ \ket $ 時，才適用 {537} 。</span><span class="sxs-lookup"><span data-stu-id="0e016-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>