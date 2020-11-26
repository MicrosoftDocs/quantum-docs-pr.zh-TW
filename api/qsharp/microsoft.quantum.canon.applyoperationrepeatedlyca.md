---
uid: Microsoft.Quantum.Canon.ApplyOperationRepeatedlyCA
title: ApplyOperationRepeatedlyCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOperationRepeatedlyCA
qsharp.summary: ''
ms.openlocfilehash: 2ff13b6b3f142437c2ca7a40884ecf1a66c6a083
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209174"
---
# <a name="applyoperationrepeatedlyca-operation"></a><span data-ttu-id="fdfd7-102">ApplyOperationRepeatedlyCA 操作</span><span class="sxs-lookup"><span data-stu-id="fdfd7-102">ApplyOperationRepeatedlyCA operation</span></span>

<span data-ttu-id="fdfd7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fdfd7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyOperationRepeatedlyCA<'T> (op : ('T => Unit is Adj + Ctl), power : Int, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fdfd7-105">輸入</span><span class="sxs-lookup"><span data-stu-id="fdfd7-105">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="fdfd7-106">op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="fdfd7-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="power--int"></a><span data-ttu-id="fdfd7-107">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-107">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="target--t"></a><span data-ttu-id="fdfd7-108">目標： t</span><span class="sxs-lookup"><span data-stu-id="fdfd7-108">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="fdfd7-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fdfd7-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fdfd7-110">類型參數</span><span class="sxs-lookup"><span data-stu-id="fdfd7-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fdfd7-111">不要</span><span class="sxs-lookup"><span data-stu-id="fdfd7-111">'T</span></span>

