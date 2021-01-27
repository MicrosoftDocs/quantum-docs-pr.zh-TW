---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: b389ca1e0737463e6ccd5ce885b849c6b32d65d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844331"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="67289-102">IdentityGeneratorIndex 函式</span><span class="sxs-lookup"><span data-stu-id="67289-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="67289-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="67289-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="67289-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67289-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67289-105">傳回與零 Hamiltonian （對應至身分識別演進作業）一致的產生器索引 `H = 0` 。</span><span class="sxs-lookup"><span data-stu-id="67289-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="67289-106">輸入</span><span class="sxs-lookup"><span data-stu-id="67289-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="67289-107">idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="67289-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="67289-108">此輸入會被忽略，而且是為了與使用者定義型別一致而定義的 <xref:microsoft.quantum.simulation.generatorsystem> 。</span><span class="sxs-lookup"><span data-stu-id="67289-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="67289-109">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="67289-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="67289-110">代表 Hamiltonian $H = $0 下演進的產生器索引。</span><span class="sxs-lookup"><span data-stu-id="67289-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>