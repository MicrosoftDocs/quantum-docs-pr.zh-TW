---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698819"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="d839d-102">Trotter2ImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="d839d-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="d839d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d839d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d839d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d839d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d839d-105">第二序位 Trotter – Suzuki 整合者的實施。</span><span class="sxs-lookup"><span data-stu-id="d839d-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="d839d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d839d-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="d839d-107">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d839d-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d839d-108">要分解為時間步驟的作業數目。</span><span class="sxs-lookup"><span data-stu-id="d839d-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="d839d-109">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d839d-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d839d-110">接受索引輸入的作業 (類型 `Int`) 和時間輸入 (類型 `Double`) ，以及量子暫存器 (類型) ， `'T` 以進行分解。</span><span class="sxs-lookup"><span data-stu-id="d839d-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="d839d-111">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d839d-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d839d-112">模擬的每個步驟大小的乘數。</span><span class="sxs-lookup"><span data-stu-id="d839d-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="d839d-113">目標： t</span><span class="sxs-lookup"><span data-stu-id="d839d-113">target : 'T</span></span>

<span data-ttu-id="d839d-114">作業作用所在的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="d839d-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d839d-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d839d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d839d-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="d839d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d839d-117">不要</span><span class="sxs-lookup"><span data-stu-id="d839d-117">'T</span></span>

<span data-ttu-id="d839d-118">每次步驟應採取的型別;通常是 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="d839d-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>