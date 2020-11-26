---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201456"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="2389a-102">GetQubitsAvailableToBorrow 操作</span><span class="sxs-lookup"><span data-stu-id="2389a-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="2389a-103">命名空間： [Microsoft. 量子. 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="2389a-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="2389a-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2389a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2389a-105">傳回目前可供借用的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="2389a-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="2389a-106">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2389a-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2389a-107">可以借用且不會配置為語句一部分的量子位數目 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="2389a-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="2389a-108">如果正在使用的目的電腦未提供此資訊，則 `-1` 會傳回。</span><span class="sxs-lookup"><span data-stu-id="2389a-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="2389a-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2389a-109">See Also</span></span>

- [<span data-ttu-id="2389a-110">GetQubitsAvailableToUse。</span><span class="sxs-lookup"><span data-stu-id="2389a-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)