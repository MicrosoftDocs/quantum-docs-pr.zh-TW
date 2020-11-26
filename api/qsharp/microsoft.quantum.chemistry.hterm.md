---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204125"
---
# <a name="hterm-user-defined-type"></a>HTerm 使用者定義型別

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


從 c # 傳遞至 Q # 的資料格式，以代表 Hamiltonian 的詞彙。
所表示資料的意義是由接收它的演算法所決定。

```qsharp

newtype HTerm = (Int[], Double[]);
```

