---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832715"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


將以單一量子位 Pauli 運算子陣列表示的多量子位 Pauli 運算子編碼為整數。

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>輸入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

最多31個單一量子位 Pauli 運算子的陣列。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

唯一識別的整數 `paulis` ，如下所述。

## <a name="remarks"></a>備註

每個 Pauli 運算子都可以使用兩個位進行編碼： $ $ \begin{align} \boldone \mapsto 00、\quad X \mapsto 01、\quad Y \mapsto 11、\quad Z \mapsto 10。
\end{align} $ $

根據 Pauli 運算子的陣列 `[P0, ..., Pn]` ，此函式會以位元組由大到小的順序串連每個 Pauli 運算子的對應，以傳回以二進位擴充形成的整數 `bits(Pn) ... bits(P0)` 。