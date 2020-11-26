---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217062"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="ce482-102">ArrangedQubits 函式</span><span class="sxs-lookup"><span data-stu-id="ce482-102">ArrangedQubits function</span></span>

<span data-ttu-id="ce482-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce482-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce482-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce482-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce482-105">根據索引排列控制項、目標和 helper 量子位</span><span class="sxs-lookup"><span data-stu-id="ce482-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="ce482-106">描述</span><span class="sxs-lookup"><span data-stu-id="ce482-106">Description</span></span>

<span data-ttu-id="ce482-107">傳回量子位陣列，其目標位於索引0，並在索引 2 ^ i 處控制 i。</span><span class="sxs-lookup"><span data-stu-id="ce482-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="ce482-108">Helper 量子位會插入陣列中的所有其他位置。</span><span class="sxs-lookup"><span data-stu-id="ce482-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="ce482-109">輸入</span><span class="sxs-lookup"><span data-stu-id="ce482-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="ce482-110">控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce482-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="ce482-111">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ce482-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="ce482-112">helper： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce482-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="ce482-113">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce482-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

