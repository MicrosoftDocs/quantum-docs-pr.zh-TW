---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 5d34bdac53870326dacb5a11c27c857793c3f420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698142"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>AssertQubitIsInStateWithinTolerance 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

包： [](https://nuget.org/packages/)


判斷提示量子位處於預期狀態。

`expected` 表示複雜向量 $ \ket{\psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $。
元組的第一個專案代表每一個 $a $，$b $ 是複數的實數部分，而第二個元素則是虛數部分。
最後一個引數定義了判斷提示的容錯。

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>輸入

### <a name="expected--complexcomplex"></a>預期： ([複雜](xref:Microsoft.Quantum.Math.Complex)、[複雜](xref:Microsoft.Quantum.Math.Complex) 的) 

$ \Ket {0} $ 和 $ \ket $ 應分別有複雜的 amplitudes {1} 。


### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)

要判斷其狀態的量子位。 請注意，此量子位假設為可與其他已配置的量子位，而非纏結。


### <a name="tolerance--double"></a>容錯： [Double](xref:microsoft.quantum.lang-ref.double)

允許實際 amplitudes 偏離預期的加法容錯。
如需詳細資訊，請參閱下面的備註。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

下列 Mathematica 程式碼可以用來驗證 mi、mx、my、mz 的運算式：

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

容錯是 \_ 3 維度實數向量 (x ₂的 $L {\infty} $ 距離。 x ₃、x ₄) 由 $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ 和實向量 (y ₂、y ₃、y ₄) 由ρ = Y ₁ I + y ₂ x + y ₃ y + y ₄ Z 定義，其中ρ是與暫存器狀態相對應的密度矩陣。
只有當 Tr (ρ) 和 Tr (| ψ⟩⟨ψ |) 都是 1 (例如 x ₁ = 1/2、y ₁ = 1/2) 。
如果不是這種情況，則函式會判斷 (x ₂-x ₁、x ₃-x ₁、x ₄-x ₁、x ₄ + x ₁) 和 (y ₂-y ₁、y ₃、y ₁ + y ₄) 小於容錯參數的 l ∞距離。