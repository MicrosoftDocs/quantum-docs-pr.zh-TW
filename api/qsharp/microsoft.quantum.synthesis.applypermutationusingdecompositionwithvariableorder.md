---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203428"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>ApplyPermutationUsingDecompositionWithVariableOrder 操作

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用以分解為基礎的合成排列，在量子狀態中 Permutes amplitudes。

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

這項作業是 @"microsoft.quantum.synthesis.applypermutationusingdecomposition" 可指定變數順序的一般版本。 不同的變數順序會變更分解順序，以及用於受控制閘道的事實資料表 @"microsoft.quantum.intrinsic.x" 。  因此，變更變數順序會變更用來實現排列的整體閘道數目。

## <a name="input"></a>輸入

### <a name="perm--int"></a>為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]

從0開始的 $ 2 ^ n $ 元素排列。


### <a name="variableorder--int"></a>variableOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]

從0開始的 $n $ 元素排列。


### <a name="qubits--littleendian"></a>量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

套用排列之 $n $ 量子位的清單。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ApplyPermutationUsingDecomposition。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [ApplyPermutationUsingTransformation。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)