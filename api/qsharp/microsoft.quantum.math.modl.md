---
uid: Microsoft.Quantum.Math.ModL
title: ModL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227789"
---
# <a name="modl-function"></a><span data-ttu-id="b2f2c-102">ModL 函式</span><span class="sxs-lookup"><span data-stu-id="b2f2c-102">ModL function</span></span>

<span data-ttu-id="b2f2c-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b2f2c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b2f2c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2f2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2f2c-105">傳回與另一個數位相關之數位的模數。</span><span class="sxs-lookup"><span data-stu-id="b2f2c-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="b2f2c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b2f2c-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="b2f2c-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2f2c-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2f2c-108">要傳回其模數的輸入 $a $。</span><span class="sxs-lookup"><span data-stu-id="b2f2c-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="b2f2c-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2f2c-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2f2c-110">要傳回 $a $ 之模數的相對數目。</span><span class="sxs-lookup"><span data-stu-id="b2f2c-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b2f2c-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b2f2c-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b2f2c-112">模數 $a \bmod b $。</span><span class="sxs-lookup"><span data-stu-id="b2f2c-112">The modulus $a \bmod b$.</span></span>