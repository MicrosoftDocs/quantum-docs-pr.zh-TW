---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699102"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="c0ce7-102">ArrangedQubits 函式</span><span class="sxs-lookup"><span data-stu-id="c0ce7-102">ArrangedQubits function</span></span>

<span data-ttu-id="c0ce7-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c0ce7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c0ce7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0ce7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c0ce7-105">根據索引排列控制項、目標和 helper 量子位</span><span class="sxs-lookup"><span data-stu-id="c0ce7-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="c0ce7-106">描述</span><span class="sxs-lookup"><span data-stu-id="c0ce7-106">Description</span></span>

<span data-ttu-id="c0ce7-107">傳回量子位陣列，其目標位於索引0，並在索引 2 ^ i 處控制 i。</span><span class="sxs-lookup"><span data-stu-id="c0ce7-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="c0ce7-108">Helper 量子位會插入陣列中的所有其他位置。</span><span class="sxs-lookup"><span data-stu-id="c0ce7-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="c0ce7-109">輸入</span><span class="sxs-lookup"><span data-stu-id="c0ce7-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="c0ce7-110">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c0ce7-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="c0ce7-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c0ce7-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="c0ce7-112">helper： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c0ce7-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="c0ce7-113">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c0ce7-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

