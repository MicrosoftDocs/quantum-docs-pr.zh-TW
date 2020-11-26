---
uid: Microsoft.Quantum.Diagnostics.Test
title: 測試使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 80821cb46d773d84085838d9ee539a8a45c43e61
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201490"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="c1360-102">測試使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="c1360-102">Test user defined type</span></span>

<span data-ttu-id="c1360-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c1360-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c1360-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c1360-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c1360-105">編譯器可辨識的屬性，可用來標記單元測試。</span><span class="sxs-lookup"><span data-stu-id="c1360-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="c1360-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="c1360-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="c1360-107">ExecutionTarget： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c1360-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

