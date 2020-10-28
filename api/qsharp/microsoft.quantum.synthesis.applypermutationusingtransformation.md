---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: b7196c592690a00da49b17f52b30536ba97b6035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701086"
---
# <a name="applypermutationusingtransformation-operation"></a>ApplyPermutationUsingTransformation 操作

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)


使用以轉換為基礎的合成排列，在量子狀態中 Permutes amplitudes。

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>描述

此程式會實行單向轉換型合成方法。  輸入是一個排列 $ \pi $ over $ 2 ^ n $ elements $ \{ 0，\dots ..，2 ^ n-1 \} $，代表 $n $-variable 可還原的布耳函數。
演算法會反復執行下列步驟：

1. 尋找最小的 $x $，$x \ne \pi (x) = y $。
2. 尋找多個控制的 Toffoli 作業（套用至輸出）會將 $ \pi (x) = x $，而不會變更所有 $x ' < x $ 的 $ \pi (x ' ) $

## <a name="input"></a>輸入

### <a name="perm--int"></a>為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]

從0開始的 $ 2 ^ n $ 元素排列。


### <a name="qubits--littleendian"></a>量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

套用排列之 $n $ 量子位的清單。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

- [*D. Michael 莎莎* 、 *Dmitri Maslov* 、 *GERHARD Dueck* 、Proc. DAC 2003、IEEE、pp 318-323、2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken* 、 *Gerhard Dueck* 、 *d. Michael 莎莎* 、Proc 2016、springer link、pp 307-321、2016](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>另請參閱

- [ApplyPermutationUsingDecomposition。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)