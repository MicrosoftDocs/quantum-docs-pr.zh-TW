---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699946"
---
# <a name="bigendian-user-defined-type"></a>BigEndian 使用者定義型別

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


以位元組由大到小的順序註冊，將不帶正負號的整數編碼。 具有索引的量子位會 `0` 將不帶正負號整數的最高位編碼。

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>備註

我們 `BigEndian` `BE` 將在檔中縮寫。