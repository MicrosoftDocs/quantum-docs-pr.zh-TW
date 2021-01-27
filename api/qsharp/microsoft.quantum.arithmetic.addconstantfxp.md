---
uid: Microsoft.Quantum.Arithmetic.AddConstantFxP
title: AddConstantFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddConstantFxP
qsharp.summary: Adds a classical constant to a quantum fixed-point number.
ms.openlocfilehash: fd985d1112298c3d2bbb0db2ff0d934098566e93
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843876"
---
# <a name="addconstantfxp-operation"></a><span data-ttu-id="8fb81-102">AddConstantFxP 操作</span><span class="sxs-lookup"><span data-stu-id="8fb81-102">AddConstantFxP operation</span></span>

<span data-ttu-id="8fb81-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8fb81-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8fb81-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="8fb81-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="8fb81-105">將傳統常數加入量子固定點數位。</span><span class="sxs-lookup"><span data-stu-id="8fb81-105">Adds a classical constant to a quantum fixed-point number.</span></span>

```qsharp
operation AddConstantFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8fb81-106">輸入</span><span class="sxs-lookup"><span data-stu-id="8fb81-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="8fb81-107">常數： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8fb81-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8fb81-108">要加入至量子固定點數位的常數。</span><span class="sxs-lookup"><span data-stu-id="8fb81-108">Constant to add to the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="8fb81-109">fp： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="8fb81-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="8fb81-110">將加入常數的固定點數位。</span><span class="sxs-lookup"><span data-stu-id="8fb81-110">Fixed-point number to which the constant will be added.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8fb81-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8fb81-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

