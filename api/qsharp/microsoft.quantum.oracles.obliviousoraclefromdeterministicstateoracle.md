---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700210"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="21d24-102">ObliviousOracleFromDeterministicStateOracle 函式</span><span class="sxs-lookup"><span data-stu-id="21d24-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="21d24-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="21d24-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="21d24-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21d24-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21d24-105">結合了 oracle `DeterministicStateOracle` 和 `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="21d24-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="21d24-106">輸入</span><span class="sxs-lookup"><span data-stu-id="21d24-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="21d24-107">ancillaOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="21d24-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="21d24-108">狀態準備 oracle $A $ 屬於 `DeterministicStateOracle` 註冊 $a $ 的型別。</span><span class="sxs-lookup"><span data-stu-id="21d24-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="21d24-109">signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="21d24-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="21d24-110">型別為的 oracle $U $ `ObliviousOracle` ，其合作于 register $a，s $。</span><span class="sxs-lookup"><span data-stu-id="21d24-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="21d24-111">輸出： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="21d24-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="21d24-112">Oracle $O = UA $ of 型別 `ObliviousOracle` 。</span><span class="sxs-lookup"><span data-stu-id="21d24-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="21d24-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21d24-113">See Also</span></span>

- [<span data-ttu-id="21d24-114">Oracle. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="21d24-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="21d24-115">Oracle. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="21d24-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)