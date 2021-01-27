---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842564"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="ad810-102">DiscreteOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="ad810-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="ad810-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ad810-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ad810-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad810-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad810-105">表示離散的 oracle。</span><span class="sxs-lookup"><span data-stu-id="ad810-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="ad810-106">這是 oracle，可針對固定作業（$U $ 和非負整數 $m $）來實 $U ^ m $。</span><span class="sxs-lookup"><span data-stu-id="ad810-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

