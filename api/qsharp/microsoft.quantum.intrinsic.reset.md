---
uid: Microsoft.Quantum.Intrinsic.Reset
title: 重設作業
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198668"
---
# <a name="reset-operation"></a><span data-ttu-id="a0b83-102">重設作業</span><span class="sxs-lookup"><span data-stu-id="a0b83-102">Reset operation</span></span>

<span data-ttu-id="a0b83-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a0b83-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a0b83-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a0b83-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a0b83-105">假設有一個量子位，請加以測量，並確保其處於 | 0 ⟩狀態，讓它可以安全地發行。</span><span class="sxs-lookup"><span data-stu-id="a0b83-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="a0b83-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a0b83-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="a0b83-107">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a0b83-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a0b83-108">量子位，其狀態會重設為 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="a0b83-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a0b83-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0b83-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

