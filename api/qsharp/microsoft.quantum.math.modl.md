---
uid: Microsoft.Quantum.Math.ModL
title: ModL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700462"
---
# <a name="modl-function"></a>ModL 函式

命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)

包： [](https://nuget.org/packages/)


傳回與另一個數位相關之數位的模數。

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a>輸入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要傳回其模數的輸入 $a $。


### <a name="b--bigint"></a>b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要傳回 $a $ 之模數的相對數目。



## <a name="output--bigint"></a>輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

模數 $a \bmod b $。