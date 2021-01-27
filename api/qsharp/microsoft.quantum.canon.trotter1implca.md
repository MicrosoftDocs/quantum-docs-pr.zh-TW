---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Trotter1ImplCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 6de4b6e7a34d66037d83a6e2bd5821402207c743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840111"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="1ef69-102">Trotter1ImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="1ef69-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="1ef69-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1ef69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1ef69-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ef69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ef69-105">第一個訂單 Trotter-Suzuki 整合者的實施。</span><span class="sxs-lookup"><span data-stu-id="1ef69-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1ef69-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1ef69-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="1ef69-107">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1ef69-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1ef69-108">要分解為時間步驟的作業數目。</span><span class="sxs-lookup"><span data-stu-id="1ef69-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="1ef69-109">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="1ef69-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1ef69-110">接受索引輸入的作業 (類型 `Int`) 和時間輸入 (類型 `Double`) ，以及量子暫存器 (類型) ， `'T` 以進行分解。</span><span class="sxs-lookup"><span data-stu-id="1ef69-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="1ef69-111">stepSize： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1ef69-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1ef69-112">模擬的每個步驟大小的乘數。</span><span class="sxs-lookup"><span data-stu-id="1ef69-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="1ef69-113">目標： t</span><span class="sxs-lookup"><span data-stu-id="1ef69-113">target : 'T</span></span>

<span data-ttu-id="1ef69-114">作業作用所在的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="1ef69-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ef69-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ef69-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1ef69-116">類型參數</span><span class="sxs-lookup"><span data-stu-id="1ef69-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1ef69-117">不要</span><span class="sxs-lookup"><span data-stu-id="1ef69-117">'T</span></span>

<span data-ttu-id="1ef69-118">每次步驟應採取的型別;通常是 `Qubit[]` 或 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="1ef69-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="1ef69-119">範例</span><span class="sxs-lookup"><span data-stu-id="1ef69-119">Example</span></span>

<span data-ttu-id="1ef69-120">以下是相等的：</span><span class="sxs-lookup"><span data-stu-id="1ef69-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT, target);
op(1, deltaT, target);
```

<span data-ttu-id="1ef69-121">及</span><span class="sxs-lookup"><span data-stu-id="1ef69-121">and</span></span>

```qsharp
Trotter1ImplCA((2, op), deltaT, target);
```