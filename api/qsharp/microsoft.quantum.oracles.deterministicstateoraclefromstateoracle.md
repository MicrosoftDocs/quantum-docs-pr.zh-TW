---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: af545a7d6e82e654ee36ab3ba77c8f8be3384b96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854547"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="f7402-102">DeterministicStateOracleFromStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="f7402-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="f7402-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="f7402-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="f7402-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7402-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7402-105">將型別的 oracle 轉換 `StateOracle` 為 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="f7402-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="f7402-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f7402-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="f7402-107">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7402-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7402-108">$A $ 之旗標量子位的索引 `stateOracle` ，它會明確地在兩個暫存器上執行：旗標 $f $ 和 system $s $，例如 $A \ket {0} \_ f\ket {\ psi} \_ s $。</span><span class="sxs-lookup"><span data-stu-id="f7402-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="f7402-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="f7402-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="f7402-110">準備 oracle $A $ 類型的狀態 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="f7402-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="f7402-111">輸出： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="f7402-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="f7402-112">Oracle 的相同狀態準備 $A $，但現在的型別是 `DeterministicStateOracle` ，因此它是在 $a 不會再明確分隔的登錄上，例如 $A \ket{0\psi} \_ {as} $。</span><span class="sxs-lookup"><span data-stu-id="f7402-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7402-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f7402-113">See Also</span></span>

- [<span data-ttu-id="f7402-114">Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="f7402-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="f7402-115">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="f7402-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)