---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839638"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="64fd0-102">HTermsToGenIdx 函式</span><span class="sxs-lookup"><span data-stu-id="64fd0-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="64fd0-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="64fd0-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="64fd0-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="64fd0-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="64fd0-105">將資料格式的 Hamiltonian 詞彙轉換成 `HTerm[]` GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="64fd0-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="64fd0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="64fd0-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="64fd0-107">data： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="64fd0-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="64fd0-108">以格式輸入資料 `HTerm[]` 。</span><span class="sxs-lookup"><span data-stu-id="64fd0-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="64fd0-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="64fd0-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="64fd0-110">新增至 GeneratorIndex 的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="64fd0-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="64fd0-111">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64fd0-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="64fd0-112">Hamiltonian 詞彙的索引</span><span class="sxs-lookup"><span data-stu-id="64fd0-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="64fd0-113">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="64fd0-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="64fd0-114">代表所表示之 Hamiltonian 詞彙的 GeneratorIndex `data[idx]` ，以及新增的其他資訊 `termType` 。</span><span class="sxs-lookup"><span data-stu-id="64fd0-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>