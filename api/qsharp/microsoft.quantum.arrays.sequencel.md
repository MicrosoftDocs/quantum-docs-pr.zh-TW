---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220258"
---
# <a name="sequencel-function"></a>SequenceL 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


取得指定間隔內的整數陣列。

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>輸入

### <a name="from--bigint"></a>from： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

間隔的內含開始索引。


### <a name="to--bigint"></a>至： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

不小於的間隔的內含結尾索引 `from` 。



## <a name="output--bigint"></a>Output： [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]

陣列，其中包含數位的序列 `from` （ `from + 1` ，...） `to` 。

## <a name="remarks"></a>備註

和之間的 `from` 差異 `to` 必須符合 `Int` 值。