---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854311"
---
# <a name="prepareuniformsuperposition-operation"></a>PrepareUniformSuperposition 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


建立以0至編碼之狀態的統一迭加 `nIndices - 1` 。

亦即，這個單一 $U $ 會根據指定的輸入狀態 $ \ket{0\cdots 0} $，在所有數位狀態 $0 $ 到 $M-$1 的情況下建立統一迭加。 換句話說，$ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}。
\end{align} $ $。

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="nindices--int"></a>nIndices： [Int](xref:microsoft.quantum.lang-ref.int)

在統一迭加中，所需的狀態數目 $M $。


### <a name="indexregister--littleendian"></a>indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以格式儲存數位狀態的量子位暫存器 `LittleEndian` 。
此暫存器必須能夠儲存 $M-$1 的數位，並假設在 state $ \ket{0\cdots 0} $ 中初始化。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>範例

下列範例會在 {1} $3 $ 量子位上準備狀態 $ \frac {\sqrt {6} } \ sum_ {j = 0} ^ {5} \ket{j} $。

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a>備註

作業是 adjointable 的，但在 `indexRegister` `nIndices` 這種情況下，必須在統一迭加中。