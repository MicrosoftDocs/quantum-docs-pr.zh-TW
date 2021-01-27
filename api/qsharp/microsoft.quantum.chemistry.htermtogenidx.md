---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839607"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="f8506-102">HTermToGenIdx 函式</span><span class="sxs-lookup"><span data-stu-id="f8506-102">HTermToGenIdx function</span></span>

<span data-ttu-id="f8506-103">命名空間： [Microsoft 量子. 化學](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f8506-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="f8506-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f8506-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f8506-105">將資料格式的 Hamiltonian 詞彙轉換 `HTerm` 成 GeneratorIndex。</span><span class="sxs-lookup"><span data-stu-id="f8506-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="f8506-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f8506-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="f8506-107">詞彙： [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="f8506-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="f8506-108">以格式輸入資料 `HTerm` 。</span><span class="sxs-lookup"><span data-stu-id="f8506-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="f8506-109">termType： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f8506-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f8506-110">新增至 GeneratorIndex 的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="f8506-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="f8506-111">輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f8506-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f8506-112">代表所表示之 Hamiltonian 詞彙的 GeneratorIndex `term` ，以及新增的其他資訊 `termType` 。</span><span class="sxs-lookup"><span data-stu-id="f8506-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>