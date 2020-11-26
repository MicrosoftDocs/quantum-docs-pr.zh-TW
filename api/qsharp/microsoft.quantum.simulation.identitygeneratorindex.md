---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229285"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="b8c20-102">IdentityGeneratorIndex 函式</span><span class="sxs-lookup"><span data-stu-id="b8c20-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="b8c20-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b8c20-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b8c20-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8c20-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8c20-105">傳回與零 Hamiltonian （對應至身分識別演進作業）一致的產生器索引 `H = 0` 。</span><span class="sxs-lookup"><span data-stu-id="b8c20-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="b8c20-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b8c20-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="b8c20-107">idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b8c20-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b8c20-108">此輸入會被忽略，而且是為了與使用者定義型別一致而定義的 <xref:microsoft.quantum.simulation.generatorsystem> 。</span><span class="sxs-lookup"><span data-stu-id="b8c20-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="b8c20-109">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="b8c20-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="b8c20-110">代表 Hamiltonian $H = $0 下演進的產生器索引。</span><span class="sxs-lookup"><span data-stu-id="b8c20-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>