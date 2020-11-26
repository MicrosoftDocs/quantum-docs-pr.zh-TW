---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199007"
---
# <a name="message-function"></a><span data-ttu-id="07499-102">Message 函數</span><span class="sxs-lookup"><span data-stu-id="07499-102">Message function</span></span>

<span data-ttu-id="07499-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="07499-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="07499-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="07499-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="07499-105">記錄訊息。</span><span class="sxs-lookup"><span data-stu-id="07499-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="07499-106">輸入</span><span class="sxs-lookup"><span data-stu-id="07499-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="07499-107">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="07499-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="07499-108">要報告的訊息。</span><span class="sxs-lookup"><span data-stu-id="07499-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07499-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07499-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="07499-110">備註</span><span class="sxs-lookup"><span data-stu-id="07499-110">Remarks</span></span>

<span data-ttu-id="07499-111">此函式的特定行為與模擬器相依，但在大部分情況下，會將指定的訊息寫入主控台。</span><span class="sxs-lookup"><span data-stu-id="07499-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>