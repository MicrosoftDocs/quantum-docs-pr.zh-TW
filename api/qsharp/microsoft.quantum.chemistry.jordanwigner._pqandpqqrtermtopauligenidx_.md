---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: c4de9593927b12b2387ae0b46513970308f59c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839317"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="efdce-102">_PQandPQQRTermToPauliGenIdx_ 函式</span><span class="sxs-lookup"><span data-stu-id="efdce-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="efdce-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="efdce-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="efdce-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="efdce-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="efdce-105">將描述 PQ 或 PQQR 詞彙的 GeneratorIndex 轉換為運算式 ' GeneratorIndex [] ' （以 Paulis 為依據）</span><span class="sxs-lookup"><span data-stu-id="efdce-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="efdce-106">輸入</span><span class="sxs-lookup"><span data-stu-id="efdce-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="efdce-107">詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="efdce-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="efdce-108">`GeneratorIndex` 代表 PQ 或 PQQR 詞彙。</span><span class="sxs-lookup"><span data-stu-id="efdce-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="efdce-109">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="efdce-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="efdce-110">將 PQ 或 PQQR 詞彙表示為 Pauli 詞彙的 ' GeneratorIndex [] '。</span><span class="sxs-lookup"><span data-stu-id="efdce-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>