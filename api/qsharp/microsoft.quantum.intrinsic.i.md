---
uid: Microsoft.Quantum.Intrinsic.I
title: I 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 5aae7a5e3b5b441829de8f10f4df539ffc374954
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198940"
---
# <a name="i-operation"></a><span data-ttu-id="69964-102">I 操作</span><span class="sxs-lookup"><span data-stu-id="69964-102">I operation</span></span>

<span data-ttu-id="69964-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="69964-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="69964-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="69964-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="69964-105">在單一量子位上執行 (無 op) 的身分識別作業。</span><span class="sxs-lookup"><span data-stu-id="69964-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="69964-106">輸入</span><span class="sxs-lookup"><span data-stu-id="69964-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="69964-107">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="69964-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="69964-108">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69964-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="69964-109">備註</span><span class="sxs-lookup"><span data-stu-id="69964-109">Remarks</span></span>

<span data-ttu-id="69964-110">這是一項無作業。</span><span class="sxs-lookup"><span data-stu-id="69964-110">This is a no-op.</span></span> <span data-ttu-id="69964-111">它是為了完整性而提供，因為有時在演算法中呼叫身分識別，或將它當作參數傳遞會很有用。</span><span class="sxs-lookup"><span data-stu-id="69964-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>