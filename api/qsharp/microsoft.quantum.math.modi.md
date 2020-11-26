---
uid: Microsoft.Quantum.Math.ModI
title: ModI 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: e0d735096ce00b97ac42b336ac226e8e25879c94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195013"
---
# <a name="modi-function"></a><span data-ttu-id="5b6a4-102">ModI 函數</span><span class="sxs-lookup"><span data-stu-id="5b6a4-102">ModI function</span></span>

<span data-ttu-id="5b6a4-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5b6a4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5b6a4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5b6a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5b6a4-105">傳回與另一個數位相關之數位的模數。</span><span class="sxs-lookup"><span data-stu-id="5b6a4-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="5b6a4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5b6a4-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5b6a4-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5b6a4-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5b6a4-108">要傳回其模數的輸入 $a $。</span><span class="sxs-lookup"><span data-stu-id="5b6a4-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="5b6a4-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5b6a4-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5b6a4-110">要傳回 $a $ 之模數的相對數目。</span><span class="sxs-lookup"><span data-stu-id="5b6a4-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="5b6a4-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5b6a4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5b6a4-112">模數 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="5b6a4-112">The modulus $a \bmod b$.</span></span>