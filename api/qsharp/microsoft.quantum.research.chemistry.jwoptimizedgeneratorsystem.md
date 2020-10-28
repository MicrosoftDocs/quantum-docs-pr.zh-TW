---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: JWOptimizedGeneratorSystem 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 8e4c06b9447a2e5838cced876febee03d1af5315
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697526"
---
# <a name="jwoptimizedgeneratorsystem-function"></a><span data-ttu-id="b72f2-102">JWOptimizedGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="b72f2-102">JWOptimizedGeneratorSystem function</span></span>

<span data-ttu-id="b72f2-103">命名空間： [Microsoft.](xref:Microsoft.Quantum.Research.Chemistry) .........。</span><span class="sxs-lookup"><span data-stu-id="b72f2-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="b72f2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b72f2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b72f2-105">將描述的 Hamiltonian 轉換為，以這個檔案中 `JWOptimizedHTerms` `GeneratorSystem` 定義的 `GeneratorIndex` 慣例表示。</span><span class="sxs-lookup"><span data-stu-id="b72f2-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="b72f2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b72f2-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="b72f2-107">資料： [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="b72f2-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="b72f2-108">格式的 Hamiltonian 描述 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="b72f2-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="b72f2-109">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b72f2-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b72f2-110">Hamiltonian 的標記法 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="b72f2-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>