---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203938"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


以偶數的建立/annihilation 運算子數目，計算 fermionic 運算子中 fermion 索引之間的約旦 Wigner 字串 Z 元件。

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>輸入

### <a name="nfermions--int"></a>nFermions： [Int](xref:microsoft.quantum.lang-ref.int)

系統中的 fermions 數目。


### <a name="idxfermions--int"></a>idxFermions： [Int](xref:microsoft.quantum.lang-ref.int)[]

fermionic 運算子索引。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` `true` 應該套用的 Bitstring `PauliZ` 。