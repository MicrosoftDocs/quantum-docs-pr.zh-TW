---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: a4f3a7b6ffa73271d7ac9674d8c718f6f09c0291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210976"
---
# <a name="complexpolar-user-defined-type"></a>ComplexPolar 使用者定義型別

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以極座標形式表示複數。

複數的極座標表示為 $c = r e ^ {i t} $。

```qsharp

newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```



## <a name="named-items"></a>命名專案

### <a name="magnitude--double"></a>大小： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)

絕對值 $r $c $ 的 \ge $0。
### <a name="argument--double"></a>引數： [Double](xref:microsoft.quantum.lang-ref.double)

階段 $t \in \mathbb R $ of $c $。