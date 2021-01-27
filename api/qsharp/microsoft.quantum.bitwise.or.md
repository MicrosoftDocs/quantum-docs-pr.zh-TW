---
uid: Microsoft.Quantum.Bitwise.Or
title: Or 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Or
qsharp.summary: Returns the bitwise OR of two integers. This performs the same computation as the built-in `|||` operator.
ms.openlocfilehash: 811e7cf64424e8302c5745c4c71d76de50ab8c08
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845272"
---
# <a name="or-function"></a><span data-ttu-id="91f98-102">Or 函式</span><span class="sxs-lookup"><span data-stu-id="91f98-102">Or function</span></span>

<span data-ttu-id="91f98-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="91f98-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="91f98-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="91f98-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="91f98-105">傳回兩個整數的位 OR。</span><span class="sxs-lookup"><span data-stu-id="91f98-105">Returns the bitwise OR of two integers.</span></span>
<span data-ttu-id="91f98-106">這會執行與內建運算子相同的計算 `|||` 。</span><span class="sxs-lookup"><span data-stu-id="91f98-106">This performs the same computation as the built-in `|||` operator.</span></span>

```qsharp
function Or (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="91f98-107">輸入</span><span class="sxs-lookup"><span data-stu-id="91f98-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="91f98-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91f98-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="91f98-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91f98-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="91f98-110">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91f98-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="91f98-111">範例</span><span class="sxs-lookup"><span data-stu-id="91f98-111">Example</span></span>

```qsharp
let a = 248;      //                 11111000₂
let b = 63;       //                 00111111₂
let x = Or(a, b); // x : Int = 255 = 11111111₂.
```

## <a name="remarks"></a><span data-ttu-id="91f98-112">備註</span><span class="sxs-lookup"><span data-stu-id="91f98-112">Remarks</span></span>

<span data-ttu-id="91f98-113">請參閱 [c # |運算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) 以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="91f98-113">See the [C# | Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/or-operator) for more details.</span></span>