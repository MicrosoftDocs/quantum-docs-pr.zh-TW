---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 183b1108ead6239e26bb0b38144cb9374e7bf285
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226752"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="e5fc9-102">DeterministicStateOracleFromStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="e5fc9-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="e5fc9-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="e5fc9-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="e5fc9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5fc9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5fc9-105">將型別的 oracle 轉換 `StateOracle` 為 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="e5fc9-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="e5fc9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e5fc9-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="e5fc9-107">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e5fc9-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e5fc9-108">$A $ 之旗標量子位的索引 `stateOracle` ，它會明確地在兩個暫存器上執行：旗標 $f $ 和 system $s $，例如 $A \ket {0} \_ f\ket {\ psi} \_ s $。</span><span class="sxs-lookup"><span data-stu-id="e5fc9-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="e5fc9-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="e5fc9-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="e5fc9-110">準備 oracle $A $ 類型的狀態 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="e5fc9-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="e5fc9-111">輸出： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="e5fc9-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="e5fc9-112">Oracle 的相同狀態準備 $A $，但現在的型別是 `DeterministicStateOracle` ，因此它是在 $a 不會再明確分隔的登錄上，例如 $A \ket{0\psi} \_ {as} $。</span><span class="sxs-lookup"><span data-stu-id="e5fc9-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5fc9-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e5fc9-113">See Also</span></span>

- [<span data-ttu-id="e5fc9-114">Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="e5fc9-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="e5fc9-115">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="e5fc9-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)