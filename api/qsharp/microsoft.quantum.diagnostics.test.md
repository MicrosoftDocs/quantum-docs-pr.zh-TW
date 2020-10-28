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
# <a name="test-user-defined-type"></a>測試使用者定義型別

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


編譯器可辨識的屬性，可用來標記單元測試。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>命名專案

### <a name="executiontarget--string"></a>ExecutionTarget： [字串](xref:microsoft.quantum.lang-ref.string)

