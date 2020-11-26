---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGeneratorImpl
title: MultiplexOperationsFromGeneratorImpl 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGeneratorImpl
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 98ba9cd24f04b8417cb176ee1630402483bc3b52
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206046"
---
# <a name="multiplexoperationsfromgeneratorimpl-operation"></a><span data-ttu-id="bc6bc-102">MultiplexOperationsFromGeneratorImpl 操作</span><span class="sxs-lookup"><span data-stu-id="bc6bc-102">MultiplexOperationsFromGeneratorImpl operation</span></span>

<span data-ttu-id="bc6bc-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bc6bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bc6bc-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc6bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc6bc-105">的執行步驟 `MultiplexOperationsFromGenerator` 。</span><span class="sxs-lookup"><span data-stu-id="bc6bc-105">Implementation step of `MultiplexOperationsFromGenerator`.</span></span>

```qsharp
operation MultiplexOperationsFromGeneratorImpl<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bc6bc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bc6bc-106">Input</span></span>

### <a name="unitarygenerator--intintint---t--unit--is-adj--ctl"></a><span data-ttu-id="bc6bc-107">unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> t => [單位](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="bc6bc-107">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="bc6bc-108">輔助： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bc6bc-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="bc6bc-109">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bc6bc-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="bc6bc-110">目標： t</span><span class="sxs-lookup"><span data-stu-id="bc6bc-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="bc6bc-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc6bc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc6bc-112">類型參數</span><span class="sxs-lookup"><span data-stu-id="bc6bc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc6bc-113">不要</span><span class="sxs-lookup"><span data-stu-id="bc6bc-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="bc6bc-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bc6bc-114">See Also</span></span>

- [<span data-ttu-id="bc6bc-115">Canon. MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="bc6bc-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)