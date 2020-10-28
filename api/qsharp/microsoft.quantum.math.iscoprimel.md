---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700234"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="9d1ed-102">IsCoprimeL 函式</span><span class="sxs-lookup"><span data-stu-id="9d1ed-102">IsCoprimeL function</span></span>

<span data-ttu-id="9d1ed-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9d1ed-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9d1ed-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d1ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d1ed-105">如果 $a $ 和 $b $ 是共同質數，則傳回 true，否則傳回 false。</span><span class="sxs-lookup"><span data-stu-id="9d1ed-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="9d1ed-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9d1ed-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="9d1ed-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9d1ed-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9d1ed-108">正在測試之共同 primality 的第一個數目</span><span class="sxs-lookup"><span data-stu-id="9d1ed-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="9d1ed-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="9d1ed-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="9d1ed-110">正在測試之共同 primality 的第二個數字</span><span class="sxs-lookup"><span data-stu-id="9d1ed-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="9d1ed-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9d1ed-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9d1ed-112">如果 $a $ 和 $b $ 是共同質數 (例如其最大公除數為 1 ) ，則為 True，否則為 false。</span><span class="sxs-lookup"><span data-stu-id="9d1ed-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>