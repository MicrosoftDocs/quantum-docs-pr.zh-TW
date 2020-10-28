---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698814"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="c3e74-102">TrotterArbitraryImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="c3e74-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="c3e74-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3e74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3e74-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3e74-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3e74-105">偶數 Trotter – Suzuki 整合器的遞迴執行。</span><span class="sxs-lookup"><span data-stu-id="c3e74-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="c3e74-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c3e74-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="c3e74-107">order： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3e74-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3e74-108">Trotter-Suzuki 整合者的順序。</span><span class="sxs-lookup"><span data-stu-id="c3e74-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="c3e74-109">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3e74-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3e74-110">要分解為時間步驟的作業數目。</span><span class="sxs-lookup"><span data-stu-id="c3e74-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="c3e74-111">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c3e74-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c3e74-112">接受索引輸入的作業 (類型 `Int`) 和時間輸入 (類型 `Double`) ，以及量子暫存器 (類型) ， `'T` 以進行分解。</span><span class="sxs-lookup"><span data-stu-id="c3e74-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c3e74-113">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c3e74-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c3e74-114">模擬的每個步驟大小的乘數。</span><span class="sxs-lookup"><span data-stu-id="c3e74-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="c3e74-115">目標： t</span><span class="sxs-lookup"><span data-stu-id="c3e74-115">target : 'T</span></span>

<span data-ttu-id="c3e74-116">作業作用所在的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="c3e74-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3e74-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3e74-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c3e74-118">類型參數</span><span class="sxs-lookup"><span data-stu-id="c3e74-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3e74-119">不要</span><span class="sxs-lookup"><span data-stu-id="c3e74-119">'T</span></span>

<span data-ttu-id="c3e74-120">每次步驟應採取的型別;通常是 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="c3e74-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>