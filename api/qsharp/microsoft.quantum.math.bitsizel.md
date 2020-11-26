---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 8b3d4cceb69619ed32977337fc0fe7401db38cbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211044"
---
# <a name="bitsizel-function"></a>BitSizeL 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


若為非負整數，則會傳回 `a` 所需的位數來表示 `a` 。

也就是說，會傳回最小的 $n $，以 $a < 2 ^ n $。

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a>輸入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要計算其位大小的整數。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

的位大小 `a` 。