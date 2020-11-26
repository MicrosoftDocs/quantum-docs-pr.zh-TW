---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214376"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients 函式

命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


展開 Jordan-Wigner 係數的 compact 標記法，以便取得這些詞彙與 Pauli 詞彙之間的一對一對應。

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>輸入

### <a name="coeff--double"></a>coeff： [Double](xref:microsoft.quantum.lang-ref.double)[]

係數的陣列，做為從 Jordan-Wigner Hamiltonian 資料結構讀取的係數。


### <a name="termtype--int"></a>termType： [Int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner 詞彙的型別。



## <a name="output--double"></a>輸出： [Double](xref:microsoft.quantum.lang-ref.double)[]

展開的係數陣列，每個 Pauli 詞彙一個。