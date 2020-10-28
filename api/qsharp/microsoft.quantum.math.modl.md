---
uid: Microsoft.Quantum.Math.ModL
title: ModL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700462"
---
# <a name="modl-function"></a><span data-ttu-id="69c79-102">ModL 函式</span><span class="sxs-lookup"><span data-stu-id="69c79-102">ModL function</span></span>

<span data-ttu-id="69c79-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="69c79-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="69c79-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69c79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69c79-105">傳回與另一個數位相關之數位的模數。</span><span class="sxs-lookup"><span data-stu-id="69c79-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="69c79-106">輸入</span><span class="sxs-lookup"><span data-stu-id="69c79-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="69c79-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69c79-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69c79-108">要傳回其模數的輸入 $a $。</span><span class="sxs-lookup"><span data-stu-id="69c79-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="69c79-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69c79-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69c79-110">要傳回 $a $ 之模數的相對數目。</span><span class="sxs-lookup"><span data-stu-id="69c79-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="69c79-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="69c79-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="69c79-112">模數 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="69c79-112">The modulus $a \bmod b$.</span></span>