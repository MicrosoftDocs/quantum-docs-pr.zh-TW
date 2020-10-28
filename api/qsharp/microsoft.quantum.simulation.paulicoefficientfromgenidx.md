---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 5bbc8d6113fb36bfd4050b98538bb61bbac02185
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699645"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="99fef-102">PauliCoefficientFromGenIdx 函式</span><span class="sxs-lookup"><span data-stu-id="99fef-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="99fef-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="99fef-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="99fef-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99fef-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99fef-105">解壓縮所描述的 Pauli 詞彙係數 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="99fef-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="99fef-106">輸入</span><span class="sxs-lookup"><span data-stu-id="99fef-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="99fef-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="99fef-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="99fef-108">`GeneratorIndex` 將 Pauli 詞彙編碼的型別。</span><span class="sxs-lookup"><span data-stu-id="99fef-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="99fef-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="99fef-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="99fef-110">所描述之詞彙的係數 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="99fef-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>