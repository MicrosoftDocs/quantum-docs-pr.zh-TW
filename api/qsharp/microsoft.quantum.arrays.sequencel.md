---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699423"
---
# <a name="sequencel-function"></a>SequenceL 函式

命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)

包： [](https://nuget.org/packages/)


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