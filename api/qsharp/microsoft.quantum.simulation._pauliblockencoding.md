---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697491"
---
# <a name="_pauliblockencoding-function"></a>_PauliBlockEncoding 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


針對 Hamiltonian 建立單一區塊編碼。

Hamiltonian $H = \ sum_ {j} \ Alpha_j P_j $ 會以 Pauli 詞彙 $P _j $ 的總和描述，每個詞彙都有實際係數 $ \ Alpha_j $。

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>輸入

### <a name="generatorsystem--generatorsystem"></a>generatorSystem： [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`，描述 $H $ 作為 Pauli 詞彙的總和


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a>statePrepUnitary： [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

單一作業 $V $，在指定函式 $f： j\rightarrow V_j $ 的情況下，套用在 index $ \ket{j} $ 上控制的單一 $V _j $。


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a>多工器： ([int](xref:microsoft.quantum.lang-ref.int)、[int](xref:microsoft.quantum.lang-ref.int) -> [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)、[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + ctl





## <a name="output--doubleblockencodingreflection"></a>輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)，[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)) 

## <a name="first-parameter"></a>第一個參數

係數 $ \Alpha = \ sum_ {j} | \ Alpha_j | $ 的一個標準。

## <a name="second-parameter"></a>第二個參數

`BlockEncodingReflection`Hamiltonian $U $ 的單一 $U $。 因為這個單一的滿足 $U ^ 2 = I $，所以也是反映。

## <a name="remarks"></a>備註

範例作業： prepare and unpreparing a state $ \ sum_ {j} \sqrt{\ Alpha_j/\Alpha}\ket{j} $，以及建立一個相乘控制的單一 <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> 和 <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> 。