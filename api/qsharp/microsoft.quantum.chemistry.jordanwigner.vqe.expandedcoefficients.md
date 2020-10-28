---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698363"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients 函式

命名空間： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

包： [](https://nuget.org/packages/)


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