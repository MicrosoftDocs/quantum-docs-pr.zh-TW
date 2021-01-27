---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846572"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian 使用者定義型別

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以位元組由小到大的順序註冊，將不帶正負號的整數編碼。 具有索引的量子位會 `0` 將不帶正負號整數的最低位編碼。

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>備註

我們 `LittleEndian` `LE` 將在檔中縮寫。