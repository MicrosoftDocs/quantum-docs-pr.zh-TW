---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842516"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="70eaf-102">ReflectionOracleFromDeterministicStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="70eaf-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="70eaf-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="70eaf-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="70eaf-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70eaf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70eaf-105">從 oracle 結構反映指定狀態的反映。</span><span class="sxs-lookup"><span data-stu-id="70eaf-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="70eaf-106">描述</span><span class="sxs-lookup"><span data-stu-id="70eaf-106">Description</span></span>

<span data-ttu-id="70eaf-107">假設有一個由單一矩陣 $O $ 所表示的決定性狀態準備 oracle，則此函式的結果為 oracle，可針對 oracle $O $; 所準備的狀態 $ \ket{\psi} $ 套用反映也就是說，state $ \ket{\psi} $，例如 $O \ket {0} = \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="70eaf-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="70eaf-108">輸入</span><span class="sxs-lookup"><span data-stu-id="70eaf-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="70eaf-109">oracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="70eaf-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="70eaf-110">準備狀態 $ \ket{\psi} $ 複本的 oracle。</span><span class="sxs-lookup"><span data-stu-id="70eaf-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="70eaf-111">輸出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="70eaf-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="70eaf-112">反映狀態 $ \ket{\psi} $ 的 oracle。</span><span class="sxs-lookup"><span data-stu-id="70eaf-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="70eaf-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="70eaf-113">See Also</span></span>

- [<span data-ttu-id="70eaf-114">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="70eaf-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="70eaf-115">Oracle. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="70eaf-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)