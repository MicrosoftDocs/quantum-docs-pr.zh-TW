---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829286"
---
# <a name="dumpoperation-operation"></a>DumpOperation 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


在指定作業的情況下，會顯示目前執行目標所提供之作業的相關診斷資訊。

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>輸入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

給定作業作用所在的量子位數目。


### <a name="op--qubit--unit--is-adj"></a>op： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞

要診斷的作業。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>範例

在量子模擬器目標上執行時，下列程式碼片段會輸出矩陣 $ $ \begin{aligned} \left ( \begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}。
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a>備註

呼叫此作業不會從 Q # 內觀察到任何效果。 顯示的確切診斷（如果有的話）取決於目前的執行目標和編輯器環境。
例如，在完整狀態量子模擬器上使用時，會顯示用來表示的單一矩陣 `op` 。

請注意，在承認全域階段不明確的模擬器上執行時 (例如：完整狀態模擬器) ，傳回的標記法可能會因全域階段而異。

同樣地，資料列和資料行矩陣表示的順序可能會與支援此作業的每個模擬器所使用的慣例不同。