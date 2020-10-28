---
uid: Microsoft.Quantum.Intrinsic.I
title: I 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 555f714047a38f49ccd94a77dc14a46d6f4988ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699614"
---
# <a name="i-operation"></a><span data-ttu-id="17271-102">I 操作</span><span class="sxs-lookup"><span data-stu-id="17271-102">I operation</span></span>

<span data-ttu-id="17271-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="17271-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="17271-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17271-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17271-105">在單一量子位上執行 (無 op) 的身分識別作業。</span><span class="sxs-lookup"><span data-stu-id="17271-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="17271-106">輸入</span><span class="sxs-lookup"><span data-stu-id="17271-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="17271-107">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="17271-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="17271-108">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17271-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="17271-109">備註</span><span class="sxs-lookup"><span data-stu-id="17271-109">Remarks</span></span>

<span data-ttu-id="17271-110">這是一項無作業。</span><span class="sxs-lookup"><span data-stu-id="17271-110">This is a no-op.</span></span> <span data-ttu-id="17271-111">它是為了完整性而提供，因為有時在演算法中呼叫身分識別，或將它當作參數傳遞會很有用。</span><span class="sxs-lookup"><span data-stu-id="17271-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>