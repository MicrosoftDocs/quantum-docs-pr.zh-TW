---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840505"
---
# <a name="graycode-function"></a>GrayCode 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


建立灰色的程式碼序列

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>輸入

### <a name="n--int"></a>n： [Int](xref:microsoft.quantum.lang-ref.int)

位數



## <a name="output--intint"></a>輸出： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []

元組的陣列。 元組中的第一個值是元組中 GrayCode 序列第二個值的值，是目前值中要變更的位置，以取得下一個值。

## <a name="example"></a>範例

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```