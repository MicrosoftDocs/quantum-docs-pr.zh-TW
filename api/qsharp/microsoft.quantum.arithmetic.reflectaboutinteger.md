---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699562"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


反映指定之傳統整數的量子暫存器。

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>描述

如果一開始是以 $ \ sum_i \ Alpha_i \ket{i} $ 表示的量子暫存器，其中每個 $ \ket{i} $ 是代表整數 $i $ 的基礎狀態，則會反映有關指定整數 $ \ket{j} $，$ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ Alpha_i \ket{i} $ $ 的基礎狀態的註冊狀態

## <a name="input"></a>輸入

### <a name="index--int"></a>index： [Int](xref:microsoft.quantum.lang-ref.int)

針對要反映之基礎狀態的傳統整數索引。


### <a name="reg--littleendian"></a>reg： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

這項作業會就地執行，而不會明確配置額外的輔助量子位。