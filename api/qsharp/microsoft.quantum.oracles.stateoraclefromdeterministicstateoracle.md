---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842511"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="f5596-102">StateOracleFromDeterministicStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="f5596-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="f5596-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="f5596-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="f5596-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5596-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5596-105">將型別的 oracle 轉換 `DeterministicStateOracle` 為 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="f5596-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="f5596-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f5596-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="f5596-107">deterministicStateOracle： [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="f5596-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="f5596-108">準備 oracle $A $ 類型的狀態 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="f5596-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="f5596-109">輸出： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="f5596-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="f5596-110">Oracle 的相同狀態準備 $A $，但現在是類型 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="f5596-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="f5596-111">請注意，在這種情況下，旗標索引 `StateOracle` 是虛擬變數，沒有任何作用。</span><span class="sxs-lookup"><span data-stu-id="f5596-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5596-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f5596-112">See Also</span></span>

- [<span data-ttu-id="f5596-113">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="f5596-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="f5596-114">Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="f5596-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)