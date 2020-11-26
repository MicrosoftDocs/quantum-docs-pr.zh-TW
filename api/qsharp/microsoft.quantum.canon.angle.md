---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219408"
---
# <a name="angle-function"></a><span data-ttu-id="7c32c-102">Angle 函數</span><span class="sxs-lookup"><span data-stu-id="7c32c-102">Angle function</span></span>

<span data-ttu-id="7c32c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c32c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c32c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c32c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c32c-105">如果的1為奇數，則傳回1，如果的值為1， `index` 則傳回-1 `index` 。</span><span class="sxs-lookup"><span data-stu-id="7c32c-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="7c32c-106">描述</span><span class="sxs-lookup"><span data-stu-id="7c32c-106">Description</span></span>

<span data-ttu-id="7c32c-107">值會對應至指定旋轉角度之指定指派的 n 變數和函式 Rademacher-Walsh 範圍之係數的正負號。</span><span class="sxs-lookup"><span data-stu-id="7c32c-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="7c32c-108">輸入</span><span class="sxs-lookup"><span data-stu-id="7c32c-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="7c32c-109">index： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7c32c-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7c32c-110">輸入指派作為整數 (從0到 2 ^ n-1) </span><span class="sxs-lookup"><span data-stu-id="7c32c-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="7c32c-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7c32c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

