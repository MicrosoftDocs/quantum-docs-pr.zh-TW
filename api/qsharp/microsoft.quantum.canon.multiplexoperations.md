---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698970"
---
# <a name="multiplexoperations-operation"></a>MultiplexOperations 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


套用由數位狀態陣列控制的作業陣列。

亦即，套用由 $U $ 的乘法控制項單一作業，以 $n $-量子位 number state $ \ket{j} $ 控制時套用單一 $V _j $。

$U = \sum ^ {2 ^ n-1-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>輸入

### <a name="unitaries--t--unit-adj--ctl"></a>unitaries： t => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl []

最多 $ 2 ^ n $ 單一作業的陣列。 $J $ th 作業是由數位狀態 $ \ket{j} $ （以位元組由小到大格式編碼）來編制索引。


### <a name="index--littleendian"></a>index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。


### <a name="target--t"></a>目標： t

$V _j $ 的一般量子位註冊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

`coefficients` 如果指定了少於 $ 2 ^ n $，將會以識別元素填補。 此實行使用 $n-$1 輔助量子位。

## <a name="references"></a>參考

- 使用量子的第一個量子模擬，Andrew M. Childs、Dmitri Maslov、Yunseong 等、Neil J. Ross、中國人民幣 Su https://arxiv.org/abs/1711.10980