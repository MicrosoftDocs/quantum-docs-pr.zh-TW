---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846237"
---
# <a name="constantarray-function"></a><span data-ttu-id="436b4-102">ConstantArray 函式</span><span class="sxs-lookup"><span data-stu-id="436b4-102">ConstantArray function</span></span>

<span data-ttu-id="436b4-103">命名空間： [Microsoft 量子。陣列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="436b4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="436b4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="436b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="436b4-105">建立指定長度的陣列，其中所有元素等於指定的值。</span><span class="sxs-lookup"><span data-stu-id="436b4-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="436b4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="436b4-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="436b4-107">長度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="436b4-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="436b4-108">新陣列的長度。</span><span class="sxs-lookup"><span data-stu-id="436b4-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="436b4-109">值： t</span><span class="sxs-lookup"><span data-stu-id="436b4-109">value : 'T</span></span>

<span data-ttu-id="436b4-110">新陣列的每個元素的值。</span><span class="sxs-lookup"><span data-stu-id="436b4-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="436b4-111">Output： t []</span><span class="sxs-lookup"><span data-stu-id="436b4-111">Output : 'T[]</span></span>

<span data-ttu-id="436b4-112">長度的新陣列 `length` ，因此每個元素都是 `value` 。</span><span class="sxs-lookup"><span data-stu-id="436b4-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="436b4-113">類型參數</span><span class="sxs-lookup"><span data-stu-id="436b4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="436b4-114">不要</span><span class="sxs-lookup"><span data-stu-id="436b4-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="436b4-115">範例</span><span class="sxs-lookup"><span data-stu-id="436b4-115">Example</span></span>

<span data-ttu-id="436b4-116">下列程式碼會建立3個布林值的陣列，每個都等於 `true` ：</span><span class="sxs-lookup"><span data-stu-id="436b4-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```