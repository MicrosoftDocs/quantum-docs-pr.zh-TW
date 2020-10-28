---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2a9bb083b121745bd556aac692d5dc85ffec3791
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698966"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a>MultiplexOperationsBruteForceFromGenerator 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


適用于 $U $ 的乘法控制項單一作業，可在由 n 量子位 number state $ \ket{j} $ 控制時套用單一 $V _j $。

$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>輸入

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a>unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int) -> t => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl) 

元組，其中第一個專案 `Int` 是 unitaries $N $ 的數目，而第二個元素 `(Int -> ('T => () is Adj + Ctl))` 是採用整數 $j $ in $ [0，n-1] $ 的函式，並輸出單一作業 $V _j $。


### <a name="index--littleendian"></a>index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。


### <a name="target--t"></a>目標： t

$V _j $ 的一般量子位註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

`coefficients` 如果指定了少於 $ 2 ^ n $，將會以識別元素填補。 此版本是直接透過透過 n 個控制的單一運算子來執行。