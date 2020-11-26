---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201405"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="c080d-102">GetQubitsAvailableToUse 操作</span><span class="sxs-lookup"><span data-stu-id="c080d-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="c080d-103">命名空間： [Microsoft. 量子. 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="c080d-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="c080d-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c080d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c080d-105">傳回目前可供使用的量子位數目。</span><span class="sxs-lookup"><span data-stu-id="c080d-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="c080d-106">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c080d-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c080d-107">可以在語句中配置的量子位數目 `using` 。</span><span class="sxs-lookup"><span data-stu-id="c080d-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="c080d-108">如果正在使用的目的電腦未提供此資訊，則 `-1` 會傳回。</span><span class="sxs-lookup"><span data-stu-id="c080d-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="c080d-109">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c080d-109">See Also</span></span>

- [<span data-ttu-id="c080d-110">GetQubitsAvailableToBorrow。</span><span class="sxs-lookup"><span data-stu-id="c080d-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)