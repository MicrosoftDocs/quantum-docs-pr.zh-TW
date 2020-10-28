---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697710"
---
# <a name="message-function"></a><span data-ttu-id="bd0f2-102">Message 函數</span><span class="sxs-lookup"><span data-stu-id="bd0f2-102">Message function</span></span>

<span data-ttu-id="bd0f2-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="bd0f2-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="bd0f2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bd0f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bd0f2-105">記錄訊息。</span><span class="sxs-lookup"><span data-stu-id="bd0f2-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bd0f2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bd0f2-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="bd0f2-107">msg： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bd0f2-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bd0f2-108">要報告的訊息。</span><span class="sxs-lookup"><span data-stu-id="bd0f2-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd0f2-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd0f2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bd0f2-110">備註</span><span class="sxs-lookup"><span data-stu-id="bd0f2-110">Remarks</span></span>

<span data-ttu-id="bd0f2-111">此函式的特定行為與模擬器相依，但在大部分情況下，會將指定的訊息寫入主控台。</span><span class="sxs-lookup"><span data-stu-id="bd0f2-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>