---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: ccbcc92d4b6f1c800b576ad54739d26665e6d6d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700982"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="268d5-102">DiscreteOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="268d5-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="268d5-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="268d5-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="268d5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="268d5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="268d5-105">表示離散的 oracle。</span><span class="sxs-lookup"><span data-stu-id="268d5-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="268d5-106">這是 oracle，可針對固定作業（$U $ 和非負整數 $m $）來實 $U ^ m $。</span><span class="sxs-lookup"><span data-stu-id="268d5-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

