---
uid: Microsoft.Quantum.Bitwise.Not
title: Not 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842106"
---
# <a name="not-function"></a><span data-ttu-id="623f4-102">Not 函式</span><span class="sxs-lookup"><span data-stu-id="623f4-102">Not function</span></span>

<span data-ttu-id="623f4-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="623f4-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="623f4-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="623f4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="623f4-105">傳回整數的位 NOT。</span><span class="sxs-lookup"><span data-stu-id="623f4-105">Returns the bitwise NOT of an integer.</span></span>
<span data-ttu-id="623f4-106">這會執行與內建運算子相同的計算 `~~~` 。</span><span class="sxs-lookup"><span data-stu-id="623f4-106">This performs the same computation as the built-in `~~~` operator.</span></span>

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="623f4-107">輸入</span><span class="sxs-lookup"><span data-stu-id="623f4-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="623f4-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="623f4-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="623f4-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="623f4-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="623f4-110">範例</span><span class="sxs-lookup"><span data-stu-id="623f4-110">Example</span></span>

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a><span data-ttu-id="623f4-111">備註</span><span class="sxs-lookup"><span data-stu-id="623f4-111">Remarks</span></span>

<span data-ttu-id="623f4-112">如需詳細資訊，請參閱 [c # ~ 運算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) 。</span><span class="sxs-lookup"><span data-stu-id="623f4-112">See the [C# ~ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) for more details.</span></span>