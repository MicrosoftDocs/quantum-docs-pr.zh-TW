---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700198"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="6e61e-102">ReflectionOracleFromDeterministicStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="6e61e-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="6e61e-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="6e61e-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="6e61e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e61e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e61e-105">從 oracle 結構反映指定狀態的反映。</span><span class="sxs-lookup"><span data-stu-id="6e61e-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="6e61e-106">描述</span><span class="sxs-lookup"><span data-stu-id="6e61e-106">Description</span></span>

<span data-ttu-id="6e61e-107">假設有一個由單一矩陣 $O $ 所表示的決定性狀態準備 oracle，則此函式的結果為 oracle，可針對 oracle $O $; 所準備的狀態 $ \ket{\psi} $ 套用反映也就是說，state $ \ket{\psi} $，例如 $O \ket {0} = \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="6e61e-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="6e61e-108">輸入</span><span class="sxs-lookup"><span data-stu-id="6e61e-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="6e61e-109">oracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="6e61e-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="6e61e-110">準備狀態 $ \ket{\psi} $ 複本的 oracle。</span><span class="sxs-lookup"><span data-stu-id="6e61e-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="6e61e-111">輸出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="6e61e-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="6e61e-112">反映狀態 $ \ket{\psi} $ 的 oracle。</span><span class="sxs-lookup"><span data-stu-id="6e61e-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e61e-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6e61e-113">See Also</span></span>

- [<span data-ttu-id="6e61e-114">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="6e61e-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="6e61e-115">Oracle. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="6e61e-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)