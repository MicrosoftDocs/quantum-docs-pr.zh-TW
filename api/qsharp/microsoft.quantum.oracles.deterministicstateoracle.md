---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842583"
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