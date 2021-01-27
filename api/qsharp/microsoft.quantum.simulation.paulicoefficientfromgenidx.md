---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: eb4f7a538e85ade4b095aa3ea5eab4448eda2491
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848000"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="794c3-102">PauliCoefficientFromGenIdx 函式</span><span class="sxs-lookup"><span data-stu-id="794c3-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="794c3-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="794c3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="794c3-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="794c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="794c3-105">解壓縮所描述的 Pauli 詞彙係數 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="794c3-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="794c3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="794c3-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="794c3-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="794c3-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="794c3-108">`GeneratorIndex` 將 Pauli 詞彙編碼的型別。</span><span class="sxs-lookup"><span data-stu-id="794c3-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="794c3-109">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="794c3-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="794c3-110">所描述之詞彙的係數 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="794c3-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>