---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698119"
---
# <a name="dumpoperation-operation"></a>DumpOperation 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


在指定作業的情況下，會顯示目前執行目標所提供之作業的相關診斷資訊。

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

給定作業作用所在的量子位數目。


### <a name="op--qubit--unit-adj"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞

要診斷的作業。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

呼叫此作業不會從 Q # 內觀察到任何效果。 顯示的確切診斷（如果有的話）取決於目前的執行目標和編輯器環境。
例如，在完整狀態量子模擬器上使用時，會顯示用來表示的單一矩陣 `op` 。

請注意，在承認全域階段不明確的模擬器上執行時 (例如：完整狀態模擬器) ，傳回的標記法可能會因全域階段而異。

同樣地，資料列和資料行矩陣表示的順序可能會與支援此作業的每個模擬器所使用的慣例不同。