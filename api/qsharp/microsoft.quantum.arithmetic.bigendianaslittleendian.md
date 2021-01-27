---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: cb4cf68753468952c7541fae23250ed1fd1914f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843373"
---
# <a name="bigendianaslittleendian-function"></a>BigEndianAsLittleEndian 函式

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


藉 `BigEndian` `LittleEndian` 由反轉量子位順序，將量子位暫存器轉換成量子位暫存器。

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a>輸入

### <a name="input--bigendian"></a>輸入： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

量子位 register `BigEndian` 格式。



## <a name="output--littleendian"></a>輸出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

量子位 register `LittleEndian` 格式。