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
# <a name="test-user-defined-type"></a>測試使用者定義型別

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


編譯器可辨識的屬性，可用來標記單元測試。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>命名專案

### <a name="executiontarget--string"></a>ExecutionTarget： [字串](xref:microsoft.quantum.lang-ref.string)

