---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223471"
---
# <a name="comparegti-operation"></a><span data-ttu-id="dd1d4-102">CompareGTI 操作</span><span class="sxs-lookup"><span data-stu-id="dd1d4-102">CompareGTI operation</span></span>

<span data-ttu-id="dd1d4-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dd1d4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dd1d4-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="dd1d4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="dd1d4-105">整數比較的包裝函式： `result = x > y` 。</span><span class="sxs-lookup"><span data-stu-id="dd1d4-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dd1d4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="dd1d4-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="dd1d4-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dd1d4-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dd1d4-108">第一個 $n $ 位數位</span><span class="sxs-lookup"><span data-stu-id="dd1d4-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="dd1d4-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dd1d4-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dd1d4-110">第二 $n $ 位數位</span><span class="sxs-lookup"><span data-stu-id="dd1d4-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="dd1d4-111">結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="dd1d4-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="dd1d4-112">如果 $x > y $，將會翻轉</span><span class="sxs-lookup"><span data-stu-id="dd1d4-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd1d4-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd1d4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

