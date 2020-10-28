---
uid: Microsoft.Quantum.Intrinsic.Reset
title: 重設作業
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699783"
---
# <a name="reset-operation"></a><span data-ttu-id="b0eed-102">重設作業</span><span class="sxs-lookup"><span data-stu-id="b0eed-102">Reset operation</span></span>

<span data-ttu-id="b0eed-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="b0eed-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="b0eed-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b0eed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b0eed-105">假設有一個量子位，請加以測量，並確保其處於 | 0 ⟩狀態，讓它可以安全地發行。</span><span class="sxs-lookup"><span data-stu-id="b0eed-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b0eed-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b0eed-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="b0eed-107">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b0eed-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b0eed-108">量子位，其狀態會重設為 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="b0eed-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0eed-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0eed-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

