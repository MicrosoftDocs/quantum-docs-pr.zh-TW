---
uid: Microsoft.Quantum.Math.ModI
title: ModI 函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: d5581c5e2e4f0bcb4f8eec78464292e23031155c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700463"
---
# <a name="modi-function"></a><span data-ttu-id="e080e-102">ModI 函數</span><span class="sxs-lookup"><span data-stu-id="e080e-102">ModI function</span></span>

<span data-ttu-id="e080e-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e080e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e080e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e080e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e080e-105">傳回與另一個數位相關之數位的模數。</span><span class="sxs-lookup"><span data-stu-id="e080e-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="e080e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e080e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e080e-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e080e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e080e-108">要傳回其模數的輸入 $a $。</span><span class="sxs-lookup"><span data-stu-id="e080e-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="e080e-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e080e-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e080e-110">要傳回 $a $ 之模數的相對數目。</span><span class="sxs-lookup"><span data-stu-id="e080e-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="e080e-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e080e-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e080e-112">模數 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="e080e-112">The modulus $a \bmod b$.</span></span>