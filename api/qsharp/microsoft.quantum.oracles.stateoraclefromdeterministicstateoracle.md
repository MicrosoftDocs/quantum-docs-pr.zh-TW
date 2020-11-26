---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193806"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="881ba-102">StateOracleFromDeterministicStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="881ba-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="881ba-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="881ba-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="881ba-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="881ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="881ba-105">將型別的 oracle 轉換 `DeterministicStateOracle` 為 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="881ba-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="881ba-106">輸入</span><span class="sxs-lookup"><span data-stu-id="881ba-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="881ba-107">deterministicStateOracle： [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="881ba-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="881ba-108">準備 oracle $A $ 類型的狀態 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="881ba-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="881ba-109">輸出： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="881ba-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="881ba-110">Oracle 的相同狀態準備 $A $，但現在是類型 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="881ba-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="881ba-111">請注意，在這種情況下，旗標索引 `StateOracle` 是虛擬變數，沒有任何作用。</span><span class="sxs-lookup"><span data-stu-id="881ba-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="881ba-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="881ba-112">See Also</span></span>

- [<span data-ttu-id="881ba-113">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="881ba-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="881ba-114">Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="881ba-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)