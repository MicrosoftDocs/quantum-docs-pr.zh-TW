---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842554"
---
# <a name="obliviousoracle-user-defined-type"></a>ObliviousOracle 使用者定義型別

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示 oracle for 無警示振幅放大。

Oracle $O $ 的輸入包括：

- $O $ 作用的 ancilla 暫存器 $a $。
- 系統註冊 $s $ （要套用所需的單一 $U $），在 register $a $ \ket{t} a $ 的 post 選取 \_ 。

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>備註

此 oracle 由 $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ 作用於 ancilla state $ \ket{s} \_ a $，以 \_ $ \ket{\psi} a $ 的基礎，以振幅 $ \lambda $ 來執行任何系統狀態 $ \ket{t} s $ 上的單一 $U $ \_ 。
第一個參數是 $ \ket{s} a $ 的量子位暫存器 \_ 。 第二個參數是 $ \ket{\psi} s $ 的量子位暫存器 \_ 。