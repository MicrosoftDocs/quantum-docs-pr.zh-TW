---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698439"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>JordanWignerInputState 使用者定義型別

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [](https://nuget.org/packages/)


從 c # 傳遞到 Q # 的資料格式，以表示準備初始狀態，表示資料的意義是由接收它的演算法所決定。

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

