---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226599"
---
# <a name="stateoracle-user-defined-type"></a>StateOracle 使用者定義型別

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


代表 oracle 的狀態準備。

Oracle $O $ 的輸入包括：

- 將旗標量子位 $f $ 索引的整數。
- 系統註冊 $s $，將會儲存所需的量子狀態 $ \ket{\psi} \_ s $。

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>備註

此 oracle 由 $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots 所定義，$ $ 作用於 on 計算基礎狀態 $ \ket {0} \_ {f} \ket {0} \_ s $，以 \_ $ \ket{\psi} {1} f $ 標示的基礎，以振幅 $ \lambda $ 來建立目標狀態 $ \ket s $ \_ 。
第一個參數是 $ \ket f $ 的量子位暫存器的索引 {0} \_ 。 第二個參數包含這兩個暫存器。