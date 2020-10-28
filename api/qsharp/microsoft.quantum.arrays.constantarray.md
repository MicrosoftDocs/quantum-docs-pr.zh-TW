---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699512"
---
# <a name="constantarray-function"></a>ConstantArray 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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

