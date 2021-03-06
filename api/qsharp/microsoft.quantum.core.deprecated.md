---
uid: Microsoft.Quantum.Core.Deprecated
title: 已淘汰的使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832075"
---
# <a name="deprecated-user-defined-type"></a>已淘汰的使用者定義型別

命名空間： [Microsoft.. 核心](xref:Microsoft.Quantum.Core)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


編譯器可辨識的屬性，可用來將類型或可呼叫標記為已被取代。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>命名專案

### <a name="newname--string"></a>NewName： [字串](xref:microsoft.quantum.lang-ref.string)

要改用之類型或可呼叫的完整名稱。
如果類型或可呼叫已被取代而沒有替代，則會設為空字串。