---
uid: Microsoft.Quantum.Bitwise.Xor
title: Xor 函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Xor
qsharp.summary: Returns the bitwise exclusive-OR (XOR) of two integers. This performs the same computation as the built-in `^^^` operator.
ms.openlocfilehash: ac31ba973ff06424dbd16168dac14a79b2691b3f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842072"
---
# <a name="xor-function"></a><span data-ttu-id="26dab-102">Xor 函數</span><span class="sxs-lookup"><span data-stu-id="26dab-102">Xor function</span></span>

<span data-ttu-id="26dab-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="26dab-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="26dab-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="26dab-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="26dab-105">傳回兩個整數的位互斥 OR (XOR) 。</span><span class="sxs-lookup"><span data-stu-id="26dab-105">Returns the bitwise exclusive-OR (XOR) of two integers.</span></span>
<span data-ttu-id="26dab-106">這會執行與內建運算子相同的計算 `^^^` 。</span><span class="sxs-lookup"><span data-stu-id="26dab-106">This performs the same computation as the built-in `^^^` operator.</span></span>

```qsharp
function Xor (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="26dab-107">輸入</span><span class="sxs-lookup"><span data-stu-id="26dab-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="26dab-108">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26dab-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="b--int"></a><span data-ttu-id="26dab-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26dab-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="26dab-110">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26dab-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="26dab-111">範例</span><span class="sxs-lookup"><span data-stu-id="26dab-111">Example</span></span>

```qsharp
let a = 248;       //                 11111000₂
let b = 63;        //                 00111111₂
let x = Xor(a, b); // x : Int = 199 = 11000111₂.
```

## <a name="remarks"></a><span data-ttu-id="26dab-112">備註</span><span class="sxs-lookup"><span data-stu-id="26dab-112">Remarks</span></span>

<span data-ttu-id="26dab-113">如需詳細資訊，請參閱 [c # ^ 運算子](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) 。</span><span class="sxs-lookup"><span data-stu-id="26dab-113">See the [C# ^ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/xor-operator) for more details.</span></span>