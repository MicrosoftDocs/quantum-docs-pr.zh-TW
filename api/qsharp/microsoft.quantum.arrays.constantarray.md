---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846237"
---
# <a name="constantarray-function"></a>ConstantArray 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


建立指定長度的陣列，其中所有元素等於指定的值。

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>輸入

### <a name="length--int"></a>長度： [Int](xref:microsoft.quantum.lang-ref.int)

新陣列的長度。


### <a name="value--t"></a>值： t

新陣列的每個元素的值。



## <a name="output--t"></a>Output： t []

長度的新陣列 `length` ，因此每個元素都是 `value` 。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="example"></a>範例

下列程式碼會建立3個布林值的陣列，每個都等於 `true` ：

```qsharp
let array = ConstantArray(3, true);
```