---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193925"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle 使用者定義型別

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示 oracle for 決定性狀態準備。

Oracle $O $ 的輸入為：

- 將儲存所需量子狀態 $ \ket{\psi} \_ s $ 的註冊。

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>備註

由 $O \ket = \ket{\psi} $ 定義的 oracle 會 {0} 在 on 計算基礎狀態 $ \ket $ 上採取動作 {0} ，以建立狀態 $ \ket{\psi} $。
第一個參數是 $ \ket{\psi} $ 的量子位暫存器。