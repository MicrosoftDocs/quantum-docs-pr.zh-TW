---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: c60c2827060f4ef223ebaf80ccdef09faaf56098
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699922"
---
# <a name="comparegti-operation"></a><span data-ttu-id="1d8dd-102">CompareGTI 操作</span><span class="sxs-lookup"><span data-stu-id="1d8dd-102">CompareGTI operation</span></span>

<span data-ttu-id="1d8dd-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1d8dd-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d8dd-105">整數比較的包裝函式： `result = x > y` 。</span><span class="sxs-lookup"><span data-stu-id="1d8dd-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1d8dd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1d8dd-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="1d8dd-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1d8dd-108">第一個 $n $ 位數位</span><span class="sxs-lookup"><span data-stu-id="1d8dd-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="1d8dd-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1d8dd-110">第二 $n $ 位數位</span><span class="sxs-lookup"><span data-stu-id="1d8dd-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="1d8dd-111">結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1d8dd-112">如果 $x > y $，將會翻轉</span><span class="sxs-lookup"><span data-stu-id="1d8dd-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d8dd-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d8dd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

