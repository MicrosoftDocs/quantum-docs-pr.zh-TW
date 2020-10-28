---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: 9bc9b4bbdab6905a6a79893b1d559425ac679400
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700807"
---
# <a name="continuousoracle-user-defined-type"></a>ContinuousOracle 使用者定義型別

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

包： [](https://nuget.org/packages/)


代表持續時間的 oracle。

這是一種 oracle，可 $U ( \delta t) ： \ket{\psi (t) } \mapsto \ket{\psi (t + \delta t) } $ 的所有時間 $t $，其中 $U $ 是固定的作業，其中 $ \delta t $ 是非負實數。

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

