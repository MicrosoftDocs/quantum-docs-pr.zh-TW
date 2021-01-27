---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827792"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="e151c-102">GetQubitsAvailableToUse 操作</span><span class="sxs-lookup"><span data-stu-id="e151c-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="e151c-103">命名空間： [Microsoft. 量子. 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="e151c-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="e151c-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e151c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e151c-105">傳回目前可供使用的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="e151c-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="e151c-106">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e151c-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e151c-107">可以在語句中配置的量子位數目 `using` 。</span><span class="sxs-lookup"><span data-stu-id="e151c-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="e151c-108">如果正在使用的目的電腦未提供此資訊，則 `-1` 會傳回。</span><span class="sxs-lookup"><span data-stu-id="e151c-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="e151c-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e151c-109">See Also</span></span>

- [<span data-ttu-id="e151c-110">GetQubitsAvailableToBorrow。</span><span class="sxs-lookup"><span data-stu-id="e151c-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)