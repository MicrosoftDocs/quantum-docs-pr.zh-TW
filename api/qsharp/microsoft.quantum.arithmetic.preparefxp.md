---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 29ba66700db83d0786a70841c7b03843a9ae6219
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222400"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="b2c07-102">PrepareFxP 操作</span><span class="sxs-lookup"><span data-stu-id="b2c07-102">PrepareFxP operation</span></span>

<span data-ttu-id="b2c07-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b2c07-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b2c07-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b2c07-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b2c07-105">將量子固定點數位初始化為傳統常數。</span><span class="sxs-lookup"><span data-stu-id="b2c07-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b2c07-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b2c07-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="b2c07-107">常數： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b2c07-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b2c07-108">要初始化量子固定點數位的常數。</span><span class="sxs-lookup"><span data-stu-id="b2c07-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="b2c07-109">fp： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="b2c07-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="b2c07-110">要初始化的 FixedPoint) 類型的固定點數位 (。</span><span class="sxs-lookup"><span data-stu-id="b2c07-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2c07-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2c07-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

