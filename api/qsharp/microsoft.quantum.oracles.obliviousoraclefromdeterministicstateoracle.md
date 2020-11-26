---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 8f1fe34e38edefba228fb9d01e1712e4c0916970
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226684"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="838cf-102">ObliviousOracleFromDeterministicStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="838cf-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="838cf-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="838cf-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="838cf-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="838cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="838cf-105">結合了 oracle `DeterministicStateOracle` 和 `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="838cf-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="838cf-106">輸入</span><span class="sxs-lookup"><span data-stu-id="838cf-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="838cf-107">ancillaOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="838cf-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="838cf-108">狀態準備 oracle $A $ 屬於 `DeterministicStateOracle` 註冊 $a $ 的型別。</span><span class="sxs-lookup"><span data-stu-id="838cf-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="838cf-109">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="838cf-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="838cf-110">型別為的 oracle $U $ `ObliviousOracle` ，其合作于 register $a，s $。</span><span class="sxs-lookup"><span data-stu-id="838cf-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="838cf-111">輸出： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="838cf-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="838cf-112">Oracle $O = UA $ of 型別 `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="838cf-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="838cf-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="838cf-113">See Also</span></span>

- [<span data-ttu-id="838cf-114">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="838cf-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="838cf-115">Oracle. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="838cf-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)