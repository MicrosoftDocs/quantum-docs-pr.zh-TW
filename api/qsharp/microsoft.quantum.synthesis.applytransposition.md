---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701078"
---
# <a name="applytransposition-operation"></a>ApplyTransposition 操作

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>描述

這項作業會以指定的 `a` `b` 狀態向量（長度為 $n $），將索引中的波幅交換至索引的波幅 `register` 。  如果 `a` 等於 `b` ，則不會變更狀態向量。

## <a name="input"></a>輸入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

第一個索引 (必須是介於0到 $ 2 ^ n-$1 之間的值) 


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

第二個索引 (必須是介於0到 $ 2 ^ n-$1 之間的值) 


### <a name="qubits--littleendian"></a>量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要套用調換的 $n $ 量子位清單。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

