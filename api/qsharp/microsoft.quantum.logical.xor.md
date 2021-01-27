---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848459"
---
# <a name="xor-function"></a><span data-ttu-id="30a8f-102">Xor 函數</span><span class="sxs-lookup"><span data-stu-id="30a8f-102">Xor function</span></span>

<span data-ttu-id="30a8f-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="30a8f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="30a8f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30a8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30a8f-105">傳回兩個值的布林專屬分隔分離。</span><span class="sxs-lookup"><span data-stu-id="30a8f-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="30a8f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="30a8f-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="30a8f-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30a8f-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30a8f-108">要考慮的第一個值。</span><span class="sxs-lookup"><span data-stu-id="30a8f-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="30a8f-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30a8f-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30a8f-110">要考慮的第二個值。</span><span class="sxs-lookup"><span data-stu-id="30a8f-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="30a8f-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30a8f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30a8f-112">`true` 只有當和都只有一個時，才 `a` `b` 會 `true` 。</span><span class="sxs-lookup"><span data-stu-id="30a8f-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>