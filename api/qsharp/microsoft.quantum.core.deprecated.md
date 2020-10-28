---
uid: Microsoft.Quantum.Core.Deprecated
title: 已淘汰的使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698238"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="7c0e1-102">已淘汰的使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="7c0e1-102">Deprecated user defined type</span></span>

<span data-ttu-id="7c0e1-103">命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="7c0e1-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="7c0e1-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c0e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c0e1-105">編譯器可辨識的屬性，可用來將類型或可呼叫標記為已被取代。</span><span class="sxs-lookup"><span data-stu-id="7c0e1-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="7c0e1-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="7c0e1-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="7c0e1-107">NewName： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7c0e1-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7c0e1-108">要改用之類型或可呼叫的完整名稱。</span><span class="sxs-lookup"><span data-stu-id="7c0e1-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="7c0e1-109">如果類型或可呼叫已被取代而沒有替代，則會設為空字串。</span><span class="sxs-lookup"><span data-stu-id="7c0e1-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>