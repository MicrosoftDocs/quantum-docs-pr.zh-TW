---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 44a6d6b63d2f6bc8b628603e78931570d1ec22eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698551"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="5a701-102">_PQandPQQRTermToPauliGenIdx_ 函式</span><span class="sxs-lookup"><span data-stu-id="5a701-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="5a701-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="5a701-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="5a701-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5a701-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5a701-105">將描述 PQ 或 PQQR 詞彙的 GeneratorIndex 轉換為運算式 ' GeneratorIndex [] ' （以 Paulis 為依據）</span><span class="sxs-lookup"><span data-stu-id="5a701-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="5a701-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5a701-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="5a701-107">詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="5a701-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="5a701-108">`GeneratorIndex` 代表 PQ 或 PQQR 詞彙。</span><span class="sxs-lookup"><span data-stu-id="5a701-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="5a701-109">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="5a701-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="5a701-110">將 PQ 或 PQQR 詞彙表示為 Pauli 詞彙的 ' GeneratorIndex [] '。</span><span class="sxs-lookup"><span data-stu-id="5a701-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>