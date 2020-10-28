---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699024"
---
# <a name="embedpauli-function"></a><span data-ttu-id="7e0e4-102">EmbedPauli 函式</span><span class="sxs-lookup"><span data-stu-id="7e0e4-102">EmbedPauli function</span></span>

<span data-ttu-id="7e0e4-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e0e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e0e4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e0e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e0e4-105">假設有一個量子位的 Pauli 運算子和一個量子位的索引，則會傳回具有指定之單一 Pauli 運算子的多重量子位量子位運算子（位於該索引和 `PauliI` 其他每個索引）。</span><span class="sxs-lookup"><span data-stu-id="7e0e4-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="7e0e4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7e0e4-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="7e0e4-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="7e0e4-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="7e0e4-108">要放在指定位置的單一量子位 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="7e0e4-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="7e0e4-109">位置： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e0e4-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e0e4-110">索引 `output[location] == pauli` ，其中 `output` 是此函數的輸出。</span><span class="sxs-lookup"><span data-stu-id="7e0e4-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="7e0e4-111">n： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e0e4-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e0e4-112">要傳回的陣列長度。</span><span class="sxs-lookup"><span data-stu-id="7e0e4-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="7e0e4-113">輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="7e0e4-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

