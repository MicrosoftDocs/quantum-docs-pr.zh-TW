---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853239"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="159b3-102">GetQubitsAvailableToBorrow 操作</span><span class="sxs-lookup"><span data-stu-id="159b3-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="159b3-103">命名空間： [Microsoft. 量子. 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="159b3-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="159b3-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="159b3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="159b3-105">傳回目前可供借用的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="159b3-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="159b3-106">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="159b3-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="159b3-107">可以借用且不會配置為語句一部分的量子位數目 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="159b3-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="159b3-108">如果正在使用的目的電腦未提供此資訊，則 `-1` 會傳回。</span><span class="sxs-lookup"><span data-stu-id="159b3-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="159b3-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="159b3-109">See Also</span></span>

- [<span data-ttu-id="159b3-110">GetQubitsAvailableToUse。</span><span class="sxs-lookup"><span data-stu-id="159b3-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)