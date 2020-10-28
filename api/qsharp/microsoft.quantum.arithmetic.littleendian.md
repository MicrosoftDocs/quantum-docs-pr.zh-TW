---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699842"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian 使用者定義型別

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


以位元組由小到大的順序註冊，將不帶正負號的整數編碼。 具有索引的量子位會 `0` 將不帶正負號整數的最低位編碼。

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>備註

我們 `LittleEndian` `LE` 將在檔中縮寫。