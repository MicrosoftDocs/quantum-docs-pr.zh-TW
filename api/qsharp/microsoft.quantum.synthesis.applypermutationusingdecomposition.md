---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 5b25ef3327bbca2dfdbe8fa876f3f797dddf77e8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192123"
---
# <a name="applypermutationusingdecomposition-operation"></a>ApplyPermutationUsingDecomposition 操作

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用以分解為基礎的合成排列，在量子狀態中 Permutes amplitudes。

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

此程式會實行以分解為基礎的合成方法。  輸入是一個排列 $ \pi $ over $ 2 ^ n $ elements $ \{ 0，\dots ..，2 ^ n-1 \} $，代表 $n $-variable 可還原的布耳函數。
演算法會針對每個變數索引反復執行下列步驟，$i $：

1. Compute $ ( # A1 \ pi_l，\ pi_r) ，\pi ' ) $，讓 $ \ pi_l $ 和 $ \ pi_r $ 的影像不會變更其專案中的位，而不是在 $i $ 和 $ \pi ' $ 的影像中變更位 $i $ 的元素。
2. Set $ \pi \leftarrow \pi ' $，並根據非固定點的元素，從 $ \ pi_l $ 和 $ \ pi_r $ 衍生事實資料表。

針對所有變數索引套用這些步驟之後，剩餘的排列 $ \pi $ 將會是身分識別，且會根據所收集的事實資料表和索引，使用作業來套用事實資料表控制 @"microsoft.quantum.intrinsic.x" 的作業 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" 。

變數順序是 $0、\dots ..、n-$1。  自訂變數順序可以在作業中指定 @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" 。

## <a name="input"></a>輸入

### <a name="perm--int"></a>為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]

從0開始的 $ 2 ^ n $ 元素排列。


### <a name="qubits--littleendian"></a>量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

套用排列之 $n $ 量子位的清單。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

- [*Alexis De Vos*、 *Yvan Van Rentergem*、進階。) 的通訊。 2 (2，2008，pp 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*、 *劉娜 Tague*、 *Gerhard W. Dueck*、 *Rolf Drechsler*、符號計算 73 (2016) 、pp 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>另請參閱

- [ApplyPermutationUsingDecompositionWithVariableOrder。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [ApplyPermutationUsingTransformation。](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)