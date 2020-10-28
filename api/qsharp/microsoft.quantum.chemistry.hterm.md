---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698694"
---
# <a name="hterm-user-defined-type"></a>HTerm 使用者定義型別

命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)

包： [](https://nuget.org/packages/)


從 c # 傳遞至 Q # 的資料格式，以代表 Hamiltonian 的詞彙。
所表示資料的意義是由接收它的演算法所決定。

```qsharp

newtype HTerm = (Int[], Double[]);
```

