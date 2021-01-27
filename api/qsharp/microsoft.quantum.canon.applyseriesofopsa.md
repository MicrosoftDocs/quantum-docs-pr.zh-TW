---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844658"
---
# <a name="applyseriesofopsa-operation"></a>ApplySeriesOfOpsA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


依序在陣列上套用 ops 清單和其目標。  (Adjoint) 

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a>輸入

### <a name="listofops--t--unit--is-adj"></a>listOfOps： t [] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 []

要套用的 ops 清單（每個都有一個 t 陣列）。 它們會依序套用，最小的索引優先。
每個都必須有 adjoint 仿函數


### <a name="targets--int"></a>目標： [Int](xref:microsoft.quantum.lang-ref.int)[] []

描述 op 目標的嵌套陣列。 每個陣列都應該包含描述要使用之索引的整數清單。


### <a name="register--t"></a>register： t []

要處理的量子位 register。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="example"></a>範例

下列適用于 Exp ( [PauliX，PauliY]，0.5) 至量子位0、1//then X 至量子位 2 let ops = [Exp ( [PauliX，PauliY]，0.5，_) ，ApplyToFirstQubitA (X，_) ];let 索引 = [[0，1]，[2]];ApplySeriesOfOpsA (ops、索引、qubitArray) ;

## <a name="see-also"></a>另請參閱

- [Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)