---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202918"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="555bd-102">SizeAdjustedTruthTable 函式</span><span class="sxs-lookup"><span data-stu-id="555bd-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="555bd-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="555bd-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="555bd-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="555bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="555bd-105">根據變數數目，從布林值陣列調整事實資料表</span><span class="sxs-lookup"><span data-stu-id="555bd-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="555bd-106">會傳回長度為的新陣列 `2^numVars` ，可能需要以 `table` 專案擴充大小， `false` 或將它截斷為 `2^numVars` 元素。</span><span class="sxs-lookup"><span data-stu-id="555bd-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="555bd-107">輸入</span><span class="sxs-lookup"><span data-stu-id="555bd-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="555bd-108">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="555bd-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="555bd-109">事實資料表作為真實值的陣列</span><span class="sxs-lookup"><span data-stu-id="555bd-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="555bd-110">numVars： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="555bd-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="555bd-111">變數數目</span><span class="sxs-lookup"><span data-stu-id="555bd-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="555bd-112">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="555bd-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="555bd-113">調整真大小的事實資料表</span><span class="sxs-lookup"><span data-stu-id="555bd-113">Size adjusted truth table</span></span>