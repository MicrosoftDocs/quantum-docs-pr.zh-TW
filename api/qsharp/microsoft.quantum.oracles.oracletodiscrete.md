---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700787"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="d1ece-102">OracleToDiscrete 函式</span><span class="sxs-lookup"><span data-stu-id="d1ece-102">OracleToDiscrete function</span></span>

<span data-ttu-id="d1ece-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="d1ece-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="d1ece-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1ece-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1ece-105">假設有一個代表「黑箱」 oracle 的作業，則會傳回代表「黑箱」 oracle 重複多次的獨立時間 oracle。</span><span class="sxs-lookup"><span data-stu-id="d1ece-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="d1ece-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d1ece-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="d1ece-107">blackBoxOracle： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d1ece-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d1ece-108">要 exponentiated 的作業。</span><span class="sxs-lookup"><span data-stu-id="d1ece-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="d1ece-109">輸出： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="d1ece-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="d1ece-110">部分套用於 "黑色 box" oracle 的作業，代表獨立時間的 oracle</span><span class="sxs-lookup"><span data-stu-id="d1ece-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>