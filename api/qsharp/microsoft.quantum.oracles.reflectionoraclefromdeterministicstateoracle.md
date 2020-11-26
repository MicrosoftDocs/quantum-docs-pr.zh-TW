---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193823"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="78485-102">ReflectionOracleFromDeterministicStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="78485-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="78485-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="78485-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="78485-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78485-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78485-105">從 oracle 結構反映指定狀態的反映。</span><span class="sxs-lookup"><span data-stu-id="78485-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="78485-106">描述</span><span class="sxs-lookup"><span data-stu-id="78485-106">Description</span></span>

<span data-ttu-id="78485-107">假設有一個由單一矩陣 $O $ 所表示的決定性狀態準備 oracle，則此函式的結果為 oracle，可針對 oracle $O $; 所準備的狀態 $ \ket{\psi} $ 套用反映也就是說，state $ \ket{\psi} $，例如 $O \ket {0} = \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="78485-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="78485-108">輸入</span><span class="sxs-lookup"><span data-stu-id="78485-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="78485-109">oracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="78485-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="78485-110">準備狀態 $ \ket{\psi} $ 複本的 oracle。</span><span class="sxs-lookup"><span data-stu-id="78485-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="78485-111">輸出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="78485-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="78485-112">反映狀態 $ \ket{\psi} $ 的 oracle。</span><span class="sxs-lookup"><span data-stu-id="78485-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="78485-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="78485-113">See Also</span></span>

- [<span data-ttu-id="78485-114">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="78485-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="78485-115">Oracle. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="78485-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)