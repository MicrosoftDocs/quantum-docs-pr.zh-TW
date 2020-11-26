---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207032"
---
# <a name="embedpauli-function"></a>EmbedPauli 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設有一個量子位的 Pauli 運算子和一個量子位的索引，則會傳回具有指定之單一 Pauli 運算子的多重量子位量子位運算子（位於該索引和 `PauliI` 其他每個索引）。

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>輸入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

要放在指定位置的單一量子位 Pauli 運算子。


### <a name="location--int"></a>位置： [Int](xref:microsoft.quantum.lang-ref.int)

索引 `output[location] == pauli` ，其中 `output` 是此函數的輸出。


### <a name="n--int"></a>n： [Int](xref:microsoft.quantum.lang-ref.int)

要傳回的陣列長度。



## <a name="output--pauli"></a>輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

