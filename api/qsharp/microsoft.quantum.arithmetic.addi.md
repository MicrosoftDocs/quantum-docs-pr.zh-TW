---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700055"
---
# <a name="addi-operation"></a>AddI 操作

命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)

包： [](https://nuget.org/packages/)


視的註冊大小而定，自動選擇 [包含] 或 [無] `ys` 。

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit 加數。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

至少有 $n $ 量子位的加數。 將會保留結果。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

