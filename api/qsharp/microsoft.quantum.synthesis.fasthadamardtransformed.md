---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203088"
---
# <a name="fasthadamardtransformed-function"></a>FastHadamardTransformed 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


{-1,1}使用 Yates 的方法，以編碼方式計算布耳函數的 Hadamard 轉換

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a>輸入

### <a name="func--int"></a>func： [Int](xref:microsoft.quantum.lang-ref.int)[]

編碼中的事實資料表 {-1,1}



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

函數的光譜系數