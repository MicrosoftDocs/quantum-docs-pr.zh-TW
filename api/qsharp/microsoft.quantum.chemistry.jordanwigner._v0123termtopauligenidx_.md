---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 8893d7c5479409a0ff98aa0b9e58f34fd3d274f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839182"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="522ff-102">_V0123TermToPauliGenIdx_ 函式</span><span class="sxs-lookup"><span data-stu-id="522ff-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="522ff-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="522ff-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="522ff-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="522ff-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="522ff-105">根據 Paulis 將描述 PQRS 詞彙的 GeneratorIndex 轉換為運算式 ' GeneratorIndex [] '</span><span class="sxs-lookup"><span data-stu-id="522ff-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="522ff-106">輸入</span><span class="sxs-lookup"><span data-stu-id="522ff-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="522ff-107">詞彙： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="522ff-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="522ff-108">`GeneratorIndex` 代表 PQRS 字詞。</span><span class="sxs-lookup"><span data-stu-id="522ff-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="522ff-109">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="522ff-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="522ff-110">將 PQRS 詞彙表示為 Pauli 詞彙的 ' GeneratorIndex [] '。</span><span class="sxs-lookup"><span data-stu-id="522ff-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>