---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700779"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="ba08d-102">StateOracleFromDeterministicStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="ba08d-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="ba08d-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ba08d-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ba08d-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba08d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba08d-105">將型別的 oracle 轉換 `DeterministicStateOracle` 為 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="ba08d-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="ba08d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ba08d-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="ba08d-107">deterministicStateOracle： [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="ba08d-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="ba08d-108">準備 oracle $A $ 類型的狀態 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="ba08d-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="ba08d-109">輸出： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="ba08d-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="ba08d-110">Oracle 的相同狀態準備 $A $，但現在是類型 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="ba08d-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="ba08d-111">請注意，在這種情況下，旗標索引 `StateOracle` 是虛擬變數，沒有任何作用。</span><span class="sxs-lookup"><span data-stu-id="ba08d-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba08d-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ba08d-112">See Also</span></span>

- [<span data-ttu-id="ba08d-113">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="ba08d-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="ba08d-114">Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="ba08d-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)