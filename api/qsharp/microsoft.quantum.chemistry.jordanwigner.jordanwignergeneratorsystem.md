---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: a75d46ef0b38fbcef99b7ab22454e1b5a9475b11
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837783"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="52638-102">JordanWignerGeneratorSystem 函式</span><span class="sxs-lookup"><span data-stu-id="52638-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="52638-103">命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="52638-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="52638-104">封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="52638-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="52638-105">將描述的 Hamiltonian 轉換為，以這個檔案中 `JWOptimizedHTerms` `GeneratorSystem` 定義的 `GeneratorIndex` 慣例表示。</span><span class="sxs-lookup"><span data-stu-id="52638-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="52638-106">輸入</span><span class="sxs-lookup"><span data-stu-id="52638-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="52638-107">資料： [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="52638-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="52638-108">格式的 Hamiltonian 描述 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="52638-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="52638-109">輸出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="52638-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="52638-110">Hamiltonian 的標記法 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="52638-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>