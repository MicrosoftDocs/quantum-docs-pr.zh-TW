---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698266"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt 函式

命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)

包： [](https://nuget.org/packages/)


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