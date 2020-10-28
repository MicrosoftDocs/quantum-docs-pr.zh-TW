---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700790"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="4092c-102">DeterministicStateOracleFromStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="4092c-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="4092c-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="4092c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="4092c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4092c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4092c-105">將型別的 oracle 轉換 `StateOracle` 為 `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="4092c-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="4092c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4092c-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="4092c-107">idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4092c-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4092c-108">$A $ 之旗標量子位的索引 `stateOracle` ，它會明確地在兩個暫存器上執行：旗標 $f $ 和 system $s $，例如 $A \ket {0} \_ f\ket {\ psi} \_ s $。</span><span class="sxs-lookup"><span data-stu-id="4092c-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="4092c-109">stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="4092c-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="4092c-110">準備 oracle $A $ 類型的狀態 `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="4092c-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="4092c-111">輸出： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="4092c-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="4092c-112">Oracle 的相同狀態準備 $A $，但現在的型別是 `DeterministicStateOracle` ，因此它是在 $a 不會再明確分隔的登錄上，例如 $A \ket{0\psi} \_ {as} $。</span><span class="sxs-lookup"><span data-stu-id="4092c-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="4092c-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4092c-113">See Also</span></span>

- [<span data-ttu-id="4092c-114">Oracle. StateOracle</span><span class="sxs-lookup"><span data-stu-id="4092c-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="4092c-115">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="4092c-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)