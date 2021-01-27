---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855204"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="86214-102">WithZeroInsertedAt 函式</span><span class="sxs-lookup"><span data-stu-id="86214-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="86214-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="86214-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="86214-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86214-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86214-105">將0位插入整數</span><span class="sxs-lookup"><span data-stu-id="86214-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="86214-106">描述</span><span class="sxs-lookup"><span data-stu-id="86214-106">Description</span></span>

<span data-ttu-id="86214-107">這種作業會接受整數、插入0位 `position` ，然後以整數傳回更新的值。</span><span class="sxs-lookup"><span data-stu-id="86214-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="86214-108">例如，在數位 10 ($10 _ = 1010_ $) 的位置2插入0會傳回 {10} {2} 數位 18 ($18 _ {10} = 10010_ {2} $) 。</span><span class="sxs-lookup"><span data-stu-id="86214-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="86214-109">輸入</span><span class="sxs-lookup"><span data-stu-id="86214-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="86214-110">position： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="86214-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="86214-111">插入0的位置</span><span class="sxs-lookup"><span data-stu-id="86214-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="86214-112">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="86214-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="86214-113">修改過的值</span><span class="sxs-lookup"><span data-stu-id="86214-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="86214-114">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="86214-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="86214-115">修改過的值</span><span class="sxs-lookup"><span data-stu-id="86214-115">Modified value</span></span>