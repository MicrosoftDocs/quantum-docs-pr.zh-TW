---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855328"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="12dc0-102">SizeAdjustedTruthTable 函式</span><span class="sxs-lookup"><span data-stu-id="12dc0-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="12dc0-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="12dc0-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="12dc0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12dc0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12dc0-105">根據變數數目，從布林值陣列調整事實資料表</span><span class="sxs-lookup"><span data-stu-id="12dc0-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="12dc0-106">會傳回長度為的新陣列 `2^numVars` ，可能需要以 `table` 專案擴充大小， `false` 或將它截斷為 `2^numVars` 元素。</span><span class="sxs-lookup"><span data-stu-id="12dc0-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="12dc0-107">輸入</span><span class="sxs-lookup"><span data-stu-id="12dc0-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="12dc0-108">table： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="12dc0-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="12dc0-109">事實資料表作為真實值的陣列</span><span class="sxs-lookup"><span data-stu-id="12dc0-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="12dc0-110">numVars： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="12dc0-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="12dc0-111">變數數目</span><span class="sxs-lookup"><span data-stu-id="12dc0-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="12dc0-112">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="12dc0-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="12dc0-113">調整真大小的事實資料表</span><span class="sxs-lookup"><span data-stu-id="12dc0-113">Size adjusted truth table</span></span>