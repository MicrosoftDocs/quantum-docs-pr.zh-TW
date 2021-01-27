---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7edf37a81571dfa1d4cb755493e1863a44c694e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857707"
---
# <a name="bitsizei-function"></a>BitSizeI 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


若為非負整數，則會傳回 `a` 所需的位數來表示 `a` 。

也就是說，會傳回最小的 $n $，以 $a < 2 ^ n $。

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要計算其位大小的整數。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

的位大小 `a` 。