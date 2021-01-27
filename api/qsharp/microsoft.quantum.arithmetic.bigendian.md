---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843385"
---
# <a name="bigendian-user-defined-type"></a>BigEndian 使用者定義型別

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以位元組由大到小的順序註冊，將不帶正負號的整數編碼。 具有索引的量子位會 `0` 將不帶正負號整數的最高位編碼。

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>備註

我們 `BigEndian` `BE` 將在檔中縮寫。