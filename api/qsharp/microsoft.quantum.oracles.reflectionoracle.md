---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226650"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle 使用者定義型別

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示反映 oracle。

反映 oracle （$O $）有輸入：

- 用來旋轉反映子空間的階段 $ \phi $。
- 要在其上執行給定反映的量子位註冊。

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>命名專案

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection： ([Double](xref:microsoft.quantum.lang-ref.double)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl



## <a name="remarks"></a>備註

此 oracle $O = \boldone- (1-e ^ {i \phi} ) \ket{\psi}\bra{\psi} $ 會透過階段 $ \phi $ 來執行部分反映，大約是單一的純狀態 $ \ket{\psi} $。