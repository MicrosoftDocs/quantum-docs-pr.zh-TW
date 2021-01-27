---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: c89288e1eb421fd5abd8fcd5d9c12049aa47ac89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843081"
---
# <a name="littleendianasbigendian-function"></a>LittleEndianAsBigEndian 函式

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


藉 `LittleEndian` `BigEndian` 由反轉量子位順序，將量子位暫存器轉換成量子位暫存器。

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a>輸入

### <a name="input--littleendian"></a>輸入： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

量子位 register `LittleEndian` 格式。



## <a name="output--bigendian"></a>輸出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

量子位 register `BigEndian` 格式。