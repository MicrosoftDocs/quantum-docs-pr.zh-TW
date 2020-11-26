---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 81993a7449098c03639cf090fb36ed39c6ba17c0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214682"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>JordanWignerInputState 使用者定義型別

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


從 c # 傳遞到 Q # 的資料格式，以表示準備初始狀態，表示資料的意義是由接收它的演算法所決定。

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

