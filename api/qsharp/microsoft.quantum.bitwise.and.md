---
uid: Microsoft.Quantum.Bitwise.And
title: And 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: And
qsharp.summary: Returns the bitwise AND of two integers. This performs the same computation as the built-in `&&&` operator.
ms.openlocfilehash: 56eae4ef222a6593fd97966a9af21d559f613bc3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842156"
---
# <a name="and-function"></a><span data-ttu-id="bbcea-102">And 函式</span><span class="sxs-lookup"><span data-stu-id="bbcea-102">And function</span></span>

<span data-ttu-id="bbcea-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="bbcea-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="bbcea-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bbcea-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bbcea-105">傳回兩個整數的位 AND。</span><span class="sxs-lookup"><span data-stu-id="bbcea-105">Returns the bitwise AND of two integers.</span></span>
<span data-ttu-id="bbcea-106">這會執行與內建運算子相同的計算 `&&&` 。</span><span class="sxs-lookup"><span data-stu-id="bbcea-106">This performs the same computation as the built-in `&&&` operator.</span></span>

```qsharp
function And (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="bbcea-107">輸入</span><span class="sxs-lookup"><span data-stu-id="bbcea-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="bbcea-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bbcea-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="bbcea-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bbcea-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="bbcea-110">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bbcea-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="bbcea-111">範例</span><span class="sxs-lookup"><span data-stu-id="bbcea-111">Example</span></span>

```qsharp
let a = 248;       //                11111000₂
let b = 63;        //                00111111₂
let x = And(a, b); // x : Int = 56 = 00111000₂.
```

## <a name="remarks"></a><span data-ttu-id="bbcea-112">備註</span><span class="sxs-lookup"><span data-stu-id="bbcea-112">Remarks</span></span>

<span data-ttu-id="bbcea-113">如需詳細資訊，請參閱 [c # &amp; 運算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (二進位) 。</span><span class="sxs-lookup"><span data-stu-id="bbcea-113">See the [C# &amp; Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/and-operator) (binary) for more details.</span></span>