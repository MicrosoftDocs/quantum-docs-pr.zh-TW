---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TimeDependentBlockEncoding 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: e2b191a4fc44f99c88f25da9b1ee6460d936740b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814272"
---
# <a name="timedependentblockencoding-user-defined-type"></a>TimeDependentBlockEncoding 使用者定義型別

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示由時鐘暫存器所 `BlockEncoding` 控制的。

也就是說，a `TimeDependentBlockEncoding` 是由 state $ \ket{k} _d $ in clock register 所控制的單一 $U $，如此一來，在系統暫存器 `d` 上作用的任意運算子 $H _k $， `s` 會在對應至輔助狀態 $ \ket _a $ 的左上角區塊中進行編碼 {0} 。 那是

$ $ \begin{align} ( \bra {0} \_ a\otimes I_ {ds} ) U ( \ket {0} \_ a\otimes I_ {ds} ) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k。
\end{align} $ $。

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

