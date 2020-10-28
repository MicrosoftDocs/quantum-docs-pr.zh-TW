---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701047"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="d8345-102">WithZeroInsertedAt 函式</span><span class="sxs-lookup"><span data-stu-id="d8345-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="d8345-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d8345-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d8345-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8345-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8345-105">將0位插入整數</span><span class="sxs-lookup"><span data-stu-id="d8345-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="d8345-106">描述</span><span class="sxs-lookup"><span data-stu-id="d8345-106">Description</span></span>

<span data-ttu-id="d8345-107">這種作業會接受整數、插入0位 `position` ，然後以整數傳回更新的值。</span><span class="sxs-lookup"><span data-stu-id="d8345-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="d8345-108">例如，在數位 10 ($10 _ = 1010_ $) 的位置2插入0會傳回 {10} {2} 數位 18 ($18 _ {10} = 10010_ {2} $) 。</span><span class="sxs-lookup"><span data-stu-id="d8345-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="d8345-109">輸入</span><span class="sxs-lookup"><span data-stu-id="d8345-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="d8345-110">position： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8345-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8345-111">插入0的位置</span><span class="sxs-lookup"><span data-stu-id="d8345-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="d8345-112">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8345-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8345-113">修改過的值</span><span class="sxs-lookup"><span data-stu-id="d8345-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="d8345-114">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8345-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8345-115">修改過的值</span><span class="sxs-lookup"><span data-stu-id="d8345-115">Modified value</span></span>