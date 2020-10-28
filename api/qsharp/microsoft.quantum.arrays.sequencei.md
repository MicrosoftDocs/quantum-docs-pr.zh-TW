---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699426"
---
# <a name="sequencei-function"></a>SequenceI 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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