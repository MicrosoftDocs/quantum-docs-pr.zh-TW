---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1f9567f327b5afc3054acbf1a615b44a54453004
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698543"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="011d8-102">_PQTermToPauliGenIdx_ 函式</span><span class="sxs-lookup"><span data-stu-id="011d8-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="011d8-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="011d8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="011d8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="011d8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="011d8-105">根據 Paulis 將描述 PQ 詞彙的 GeneratorIndex 轉換為運算式 ' GeneratorIndex [] '</span><span class="sxs-lookup"><span data-stu-id="011d8-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="011d8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="011d8-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="011d8-107">詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="011d8-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="011d8-108">`GeneratorIndex` 代表 PQ 字詞。</span><span class="sxs-lookup"><span data-stu-id="011d8-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="011d8-109">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="011d8-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="011d8-110">將 PQ 詞彙表示為 Pauli 詞彙的 ' GeneratorIndex [] '。</span><span class="sxs-lookup"><span data-stu-id="011d8-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>