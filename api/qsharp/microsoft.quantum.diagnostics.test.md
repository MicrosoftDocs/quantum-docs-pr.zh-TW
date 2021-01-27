---
uid: Microsoft.Quantum.Diagnostics.Test
title: 測試使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 2f1b521c4ef2bf8e672ca4fe7a5f380d744300b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853263"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="0e584-102">測試使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="0e584-102">Test user defined type</span></span>

<span data-ttu-id="0e584-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0e584-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0e584-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0e584-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0e584-105">編譯器可辨識的屬性，可用來標記單元測試。</span><span class="sxs-lookup"><span data-stu-id="0e584-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="0e584-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="0e584-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="0e584-107">ExecutionTarget： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0e584-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

