---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 6614b78c8e64c205cc94052cc64dd957814ab3d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700739"
---
# <a name="blochspherecoordinates-function"></a>BlochSphereCoordinates 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


計算單一量子位狀態的布洛赫球體座標。

假設有兩個複數 $a 0，a1 $ 表示量子位狀態，則會計算布洛赫球體上的座標，例如 $a 0 \ket {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i \phi/2}\cos{ ( \ theta/2) } \ket {0} + e ^ {i \phi/2}\sin{ ( \ theta/2) } \ket {1}) $。

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a>輸入

### <a name="a0--complexpolar"></a>a0： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

狀態 $ \ket $ 的複數係數 {0} 。


### <a name="a1--complexpolar"></a>a1： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)

狀態 $ \ket $ 的複數係數 {1} 。



## <a name="output--complexpolardoubledouble"></a>輸出： ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)、[double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double)) 

包含的元組 `(ComplexPolar(r, t), phi, theta)` 。