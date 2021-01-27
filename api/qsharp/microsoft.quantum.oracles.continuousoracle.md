---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: ac254b7556878550216d5c0c9222620fdc5c5702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855940"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="d2638-102">ContinuousOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="d2638-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="d2638-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="d2638-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="d2638-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d2638-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d2638-105">代表持續時間的 oracle。</span><span class="sxs-lookup"><span data-stu-id="d2638-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="d2638-106">這是一種 oracle，可 $U ( \delta t) ： \ket{\psi (t) } \mapsto \ket{\psi (t + \delta t) } $ 的所有時間 $t $，其中 $U $ 是固定的作業，其中 $ \delta t $ 是非負實數。</span><span class="sxs-lookup"><span data-stu-id="d2638-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

