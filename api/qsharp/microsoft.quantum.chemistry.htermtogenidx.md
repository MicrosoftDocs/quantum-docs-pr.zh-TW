---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698683"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="264d9-102">HTermToGenIdx 函式</span><span class="sxs-lookup"><span data-stu-id="264d9-102">HTermToGenIdx function</span></span>

<span data-ttu-id="264d9-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="264d9-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="264d9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="264d9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="264d9-105">將資料格式的 Hamiltonian 詞彙轉換 `HTerm` 成 GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="264d9-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="264d9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="264d9-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="264d9-107">詞彙： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="264d9-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="264d9-108">以格式輸入資料 `HTerm` 。</span><span class="sxs-lookup"><span data-stu-id="264d9-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="264d9-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="264d9-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="264d9-110">新增至 GeneratorIndex 的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="264d9-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="264d9-111">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="264d9-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="264d9-112">代表所表示之 Hamiltonian 詞彙的 GeneratorIndex `term` ，以及新增的其他資訊 `termType` 。</span><span class="sxs-lookup"><span data-stu-id="264d9-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>