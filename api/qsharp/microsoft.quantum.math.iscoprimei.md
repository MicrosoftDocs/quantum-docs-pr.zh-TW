---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700534"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="dbf42-102">IsCoprimeI 函式</span><span class="sxs-lookup"><span data-stu-id="dbf42-102">IsCoprimeI function</span></span>

<span data-ttu-id="dbf42-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dbf42-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dbf42-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dbf42-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dbf42-105">如果 $a $ 和 $b $ 是共同質數，則傳回 true，否則傳回 false。</span><span class="sxs-lookup"><span data-stu-id="dbf42-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="dbf42-106">輸入</span><span class="sxs-lookup"><span data-stu-id="dbf42-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="dbf42-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dbf42-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dbf42-108">正在測試之共同 primality 的第一個數目</span><span class="sxs-lookup"><span data-stu-id="dbf42-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="dbf42-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dbf42-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dbf42-110">正在測試之共同 primality 的第二個數字</span><span class="sxs-lookup"><span data-stu-id="dbf42-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="dbf42-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="dbf42-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="dbf42-112">如果 $a $ 和 $b $ 是共同質數 (例如其最大公除數為 1 ) ，則為 True，否則為 false。</span><span class="sxs-lookup"><span data-stu-id="dbf42-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>