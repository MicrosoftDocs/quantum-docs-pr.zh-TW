---
uid: Microsoft.Quantum.Math.ComplexPolar
title: ComplexPolar 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ComplexPolar
qsharp.summary: >-
  Represents a complex number in polar form.

  The polar representation of a complex number is $c=r e^{i t}$.
ms.openlocfilehash: 174e75b82a3ee740cd4d07e5bcd091de65bbc6b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847354"
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