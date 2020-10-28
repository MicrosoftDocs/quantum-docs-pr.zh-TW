---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698690"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="9bbde-102">HTermsToGenIdx 函式</span><span class="sxs-lookup"><span data-stu-id="9bbde-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="9bbde-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9bbde-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="9bbde-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9bbde-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9bbde-105">將資料格式的 Hamiltonian 詞彙轉換成 `HTerm[]` GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="9bbde-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="9bbde-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9bbde-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="9bbde-107">data： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="9bbde-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="9bbde-108">以格式輸入資料 `HTerm[]` 。</span><span class="sxs-lookup"><span data-stu-id="9bbde-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="9bbde-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9bbde-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9bbde-110">新增至 GeneratorIndex 的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="9bbde-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="9bbde-111">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9bbde-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9bbde-112">Hamiltonian 詞彙的索引</span><span class="sxs-lookup"><span data-stu-id="9bbde-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="9bbde-113">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9bbde-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9bbde-114">代表所表示之 Hamiltonian 詞彙的 GeneratorIndex `data[idx]` ，以及新增的其他資訊 `termType` 。</span><span class="sxs-lookup"><span data-stu-id="9bbde-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>