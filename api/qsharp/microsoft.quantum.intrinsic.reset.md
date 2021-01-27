---
uid: Microsoft.Quantum.Intrinsic.Reset
title: 重設作業
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818635"
---
# <a name="reset-operation"></a><span data-ttu-id="d2d6b-102">重設作業</span><span class="sxs-lookup"><span data-stu-id="d2d6b-102">Reset operation</span></span>

<span data-ttu-id="d2d6b-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d2d6b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d2d6b-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d2d6b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d2d6b-105">假設有一個量子位，請加以測量，並確保其處於 | 0 ⟩狀態，讓它可以安全地發行。</span><span class="sxs-lookup"><span data-stu-id="d2d6b-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d2d6b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d2d6b-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="d2d6b-107">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d2d6b-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d2d6b-108">量子位，其狀態會重設為 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="d2d6b-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d2d6b-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d2d6b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

