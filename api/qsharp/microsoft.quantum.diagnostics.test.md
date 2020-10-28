---
uid: Microsoft.Quantum.Diagnostics.Test
title: 測試使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 8030f6378ac0cb393c7ed2b9e636a7561e8943a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698058"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="aaf40-102">測試使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="aaf40-102">Test user defined type</span></span>

<span data-ttu-id="aaf40-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="aaf40-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="aaf40-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aaf40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aaf40-105">編譯器可辨識的屬性，可用來標記單元測試。</span><span class="sxs-lookup"><span data-stu-id="aaf40-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="aaf40-106">命名專案</span><span class="sxs-lookup"><span data-stu-id="aaf40-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="aaf40-107">ExecutionTarget： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="aaf40-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

