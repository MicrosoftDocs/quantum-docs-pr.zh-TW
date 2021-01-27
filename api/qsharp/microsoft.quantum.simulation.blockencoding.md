---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 70cd18f04cbd449f4818ba3b40580303137f84db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857638"
---
# <a name="blockencoding-user-defined-type"></a>BlockEncoding 使用者定義型別

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示在左上角區塊中編碼任意運算子的單一位置。

亦即，a `BlockEncoding` 是一個單一 $U $，在系統暫存器上作用的任意運算子 $H $， `s` 會在對應至輔助狀態 $ \ket _a $ 的左上角區塊中進行編碼 {0} 。 那是

$ $ \begin{align} ( \bra {0} _a \otimes I_s) U ( \ket {0} _a \otimes I_s) = H \end{align} $ $。

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

