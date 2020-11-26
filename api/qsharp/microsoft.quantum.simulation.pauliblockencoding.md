---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: b1df6d239e6ef061cf0a4784c652e9dd126991d5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230424"
---
# <a name="pauliblockencoding-function"></a>PauliBlockEncoding 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對 Hamiltonian 建立單一區塊編碼。

Hamiltonian $H = \ sum_ {j} \ Alpha_j P_j $ 會以 Pauli 詞彙 $P _j $ 的總和描述，每個詞彙都有實際係數 $ \ Alpha_j $。

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>輸入

### <a name="generatorsystem--generatorsystem"></a>generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`，描述 $H $ 作為 Pauli 詞彙的總和



## <a name="output--doubleblockencodingreflection"></a>輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)，[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)) 

## <a name="first-parameter"></a>第一個參數

係數 $ \Alpha = \ sum_ {j} | \ Alpha_j | $ 的一個標準。

## <a name="second-parameter"></a>第二個參數

`BlockEncodingReflection`Hamiltonian $H $ 的單一 $U $。 因為這個單一的滿足 $U ^ 2 = I $，所以也是反映。

## <a name="remarks"></a>備註

這是藉由準備和 unpreparing 狀態 $ \ sum_ {j} \sqrt{\ Alpha_j/\Alpha}\ket{j} $ 來取得，並且會建立相乘控制的單一 <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> 和 <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> 。