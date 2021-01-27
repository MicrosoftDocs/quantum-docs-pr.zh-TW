---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 048f91411099d24f3c0c5fd8ae3703779e7ab8a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847900"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="76c7e-102">PauliStringFromGenIdx 函式</span><span class="sxs-lookup"><span data-stu-id="76c7e-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="76c7e-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="76c7e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="76c7e-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76c7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76c7e-105">將所描述之 Pauli 詞彙的 Pauli 字串及其量子位索引解壓縮 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="76c7e-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="76c7e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="76c7e-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="76c7e-107">generatorIndex： [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="76c7e-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="76c7e-108">`GeneratorIndex` 將 Pauli 詞彙編碼的型別。</span><span class="sxs-lookup"><span data-stu-id="76c7e-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="76c7e-109">Output： ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[]，[Int](xref:microsoft.quantum.lang-ref.int)[] ) </span><span class="sxs-lookup"><span data-stu-id="76c7e-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="76c7e-110">所描述之詞彙的 Pauli 字串 `GeneratorIndex` ，以及其作用所在量子位的索引。</span><span class="sxs-lookup"><span data-stu-id="76c7e-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>