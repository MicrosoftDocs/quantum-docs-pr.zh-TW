---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: 4443af5884755f72fac6f9b76f95c3831c67b13f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207168"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="daa7b-102">DecomposeIntoTimeStepsCA 函式</span><span class="sxs-lookup"><span data-stu-id="daa7b-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="daa7b-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="daa7b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="daa7b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="daa7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="daa7b-105">DecomposeIntoTimeStepsCA 已被取代。</span><span class="sxs-lookup"><span data-stu-id="daa7b-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="daa7b-106">請改用 <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA>。</span><span class="sxs-lookup"><span data-stu-id="daa7b-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="daa7b-107">輸入</span><span class="sxs-lookup"><span data-stu-id="daa7b-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="daa7b-108">nSteps： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="daa7b-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="daa7b-109">op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="daa7b-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="daa7b-110">trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="daa7b-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="daa7b-111">輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="daa7b-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="daa7b-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="daa7b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="daa7b-113">不要</span><span class="sxs-lookup"><span data-stu-id="daa7b-113">'T</span></span>

