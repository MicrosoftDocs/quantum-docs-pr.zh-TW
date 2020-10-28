---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699055"
---
# <a name="controlledonint-function"></a><span data-ttu-id="c8dce-102">ControlledOnInt 函式</span><span class="sxs-lookup"><span data-stu-id="c8dce-102">ControlledOnInt function</span></span>

<span data-ttu-id="c8dce-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8dce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8dce-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8dce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8dce-105">傳回單一運算子，這個運算子會在目標暫存器上套用 oracle （如果控制項暫存器狀態對應到指定的正整數）。</span><span class="sxs-lookup"><span data-stu-id="c8dce-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c8dce-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c8dce-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="c8dce-107">numberState： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8dce-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8dce-108">正整數。</span><span class="sxs-lookup"><span data-stu-id="c8dce-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="c8dce-109">oracle： t => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c8dce-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c8dce-110">單一運算子。</span><span class="sxs-lookup"><span data-stu-id="c8dce-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="c8dce-111">Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，t) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c8dce-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c8dce-112">`oracle`如果控制項暫存器狀態對應至數位狀態，則會在目標暫存器上套用的單一運算子 `numberState` 。</span><span class="sxs-lookup"><span data-stu-id="c8dce-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c8dce-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="c8dce-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c8dce-114">不要</span><span class="sxs-lookup"><span data-stu-id="c8dce-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c8dce-115">備註</span><span class="sxs-lookup"><span data-stu-id="c8dce-115">Remarks</span></span>

<span data-ttu-id="c8dce-116">的值 `numberState` 是使用位元組由大到小的編碼來解讀。</span><span class="sxs-lookup"><span data-stu-id="c8dce-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>