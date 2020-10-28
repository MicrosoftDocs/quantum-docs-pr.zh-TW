---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700166"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


將轉換 `BlockEncoding` 成相等的 `BLockEncodingReflection` 。

也就是說，假設有一個 `BlockEncoding` 可將某些運算子編碼 $H $ 的單一 $U $，則會將它轉換成 `BlockEncodingReflection` 編碼相同運算子的 $U ' $，但也會滿足 $U ' ^ \Dagger = U ' $。
這會將 $U $ 的輔助暫存器大小增加一個量子位。

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>輸入

### <a name="blockencoding--blockencoding"></a>blockEncoding： [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

`BlockEncoding`要轉換成反映的單一 $U $。



## <a name="output--blockencodingreflection"></a>輸出： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

單一 $U ' $ 可共同處理暫存器 `a` ，並將 `s` $H $ 的區塊編碼，並滿足 $U ' ^ \Dagger = U ' $。

## <a name="remarks"></a>備註

這會將 $U $ 的輔助暫存器大小增加一個量子位。

## <a name="references"></a>參考

- Hamiltonian 模擬，量子位化 Guang Hao Low，Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>另請參閱

- [BlockEncoding。](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)