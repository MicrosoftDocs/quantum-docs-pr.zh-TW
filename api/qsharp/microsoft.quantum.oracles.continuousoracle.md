---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226786"
---
# <a name="continuousoracle-user-defined-type"></a>ContinuousOracle 使用者定義型別

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


代表持續時間的 oracle。

這是一種 oracle，可 $U ( \delta t) ： \ket{\psi (t) } \mapsto \ket{\psi (t + \delta t) } $ 的所有時間 $t $，其中 $U $ 是固定的作業，其中 $ \delta t $ 是非負實數。

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

