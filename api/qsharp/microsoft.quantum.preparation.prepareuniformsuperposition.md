---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697147"
---
# <a name="prepareuniformsuperposition-operation"></a>PrepareUniformSuperposition 操作

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


建立以0至編碼之狀態的統一迭加 `nIndices - 1` 。

亦即，這個單一 $U $ 會根據指定的輸入狀態 $ \ket{0\cdots 0} $，在所有數位狀態 $0 $ 到 $M-$1 的情況下建立統一迭加。 換句話說，$ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}。
\end{align} $ $。

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>輸入

### <a name="nindices--int"></a>nIndices： [Int](xref:microsoft.quantum.lang-ref.int)

在統一迭加中，所需的狀態數目 $M $。


### <a name="indexregister--littleendian"></a>indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以格式儲存數位狀態的量子位暫存器 `LittleEndian` 。
此暫存器必須能夠儲存 $M-$1 的數位，並假設在 state $ \ket{0\cdots 0} $ 中初始化。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>備註

作業是 adjointable 的，但在 `indexRegister` `nIndices` 這種情況下，必須在統一迭加中。