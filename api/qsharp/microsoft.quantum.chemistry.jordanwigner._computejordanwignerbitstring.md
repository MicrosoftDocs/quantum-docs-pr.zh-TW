---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698646"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [](https://nuget.org/packages/)


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