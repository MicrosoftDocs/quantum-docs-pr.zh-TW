---
uid: Microsoft.Quantum.Synthesis.Encoded
title: 編碼函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203173"
---
# <a name="encoded-function"></a><span data-ttu-id="a17d3-102">編碼函數</span><span class="sxs-lookup"><span data-stu-id="a17d3-102">Encoded function</span></span>

<span data-ttu-id="a17d3-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a17d3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a17d3-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a17d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a17d3-105">編碼中的事實資料表編碼 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="a17d3-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="a17d3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a17d3-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="a17d3-107">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a17d3-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a17d3-108">事實資料表作為真實值的陣列</span><span class="sxs-lookup"><span data-stu-id="a17d3-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="a17d3-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a17d3-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a17d3-110">事實資料表作為整數陣列 {1,-1}</span><span class="sxs-lookup"><span data-stu-id="a17d3-110">Truth table as array of {1,-1} integers</span></span>