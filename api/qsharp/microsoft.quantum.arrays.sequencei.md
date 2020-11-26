---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220292"
---
# <a name="sequencei-function"></a>SequenceI 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


取得指定間隔內的整數陣列。

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a>輸入

### <a name="from--int"></a>來源： [Int](xref:microsoft.quantum.lang-ref.int)

間隔的內含開始索引。


### <a name="to--int"></a>至： [Int](xref:microsoft.quantum.lang-ref.int)

不小於的間隔的內含結尾索引 `from` 。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

陣列，其中包含數位的序列 `from` （ `from + 1` ，...） `to` 。