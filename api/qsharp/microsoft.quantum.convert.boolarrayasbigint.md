---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 5a85fd9f81cec0f2de7e7807622aab9604a4db7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214308"
---
# <a name="boolarrayasbigint-function"></a>BoolArrayAsBigInt 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


將指定的布林值陣列轉換為相等的大整數。
陣列的0元素是大整數中最不重要的位。

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a>輸入

### <a name="a--bool"></a>a： [Bool](xref:microsoft.quantum.lang-ref.bool)[]





## <a name="output--bigint"></a>輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>備註

如需詳細資訊，請參閱 [c # BigInteger](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 函式。