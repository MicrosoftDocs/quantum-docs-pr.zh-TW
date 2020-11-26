---
uid: Microsoft.Quantum.Intrinsic.S
title: S 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: c697408c4efe1963787b5aee8f0d3bb6b9e64dd5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198447"
---
# <a name="s-operation"></a><span data-ttu-id="44ab1-102">S 操作</span><span class="sxs-lookup"><span data-stu-id="44ab1-102">S operation</span></span>

<span data-ttu-id="44ab1-103">命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="44ab1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="44ab1-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="44ab1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="44ab1-105">將 S 閘道套用至單一量子位。</span><span class="sxs-lookup"><span data-stu-id="44ab1-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="44ab1-106">描述</span><span class="sxs-lookup"><span data-stu-id="44ab1-106">Description</span></span>

<span data-ttu-id="44ab1-107">這項作業可由單一矩陣 \begin{align} S \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="44ab1-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="44ab1-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="44ab1-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="44ab1-109">輸入</span><span class="sxs-lookup"><span data-stu-id="44ab1-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="44ab1-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="44ab1-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="44ab1-111">應套用閘道的量子位。</span><span class="sxs-lookup"><span data-stu-id="44ab1-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="44ab1-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44ab1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

