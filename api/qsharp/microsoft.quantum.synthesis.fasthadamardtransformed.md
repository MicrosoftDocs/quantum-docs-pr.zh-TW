---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855461"
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

## <a name="example"></a>範例

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```