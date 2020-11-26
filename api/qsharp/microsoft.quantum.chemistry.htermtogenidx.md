---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216025"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="a87af-102">HTermToGenIdx 函式</span><span class="sxs-lookup"><span data-stu-id="a87af-102">HTermToGenIdx function</span></span>

<span data-ttu-id="a87af-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a87af-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="a87af-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a87af-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a87af-105">將資料格式的 Hamiltonian 詞彙轉換 `HTerm` 成 GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="a87af-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="a87af-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a87af-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="a87af-107">詞彙： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="a87af-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="a87af-108">以格式輸入資料 `HTerm` 。</span><span class="sxs-lookup"><span data-stu-id="a87af-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="a87af-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a87af-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a87af-110">新增至 GeneratorIndex 的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a87af-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="a87af-111">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a87af-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a87af-112">代表所表示之 Hamiltonian 詞彙的 GeneratorIndex `term` ，以及新增的其他資訊 `termType` 。</span><span class="sxs-lookup"><span data-stu-id="a87af-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>