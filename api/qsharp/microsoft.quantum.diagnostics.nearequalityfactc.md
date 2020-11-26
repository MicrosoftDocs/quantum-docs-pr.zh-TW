---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactC
title: NearEqualityFactC 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactC
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: b08d5edcc1ead2cd125864a157efac76b72ba0d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201609"
---
# <a name="nearequalityfactc-function"></a><span data-ttu-id="b22f6-102">NearEqualityFactC 函式</span><span class="sxs-lookup"><span data-stu-id="b22f6-102">NearEqualityFactC function</span></span>

<span data-ttu-id="b22f6-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b22f6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b22f6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b22f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b22f6-105">判斷值，傳統複數的預期值最高可達 1e-10 的小容錯。</span><span class="sxs-lookup"><span data-stu-id="b22f6-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex) : Unit
```


## <a name="input"></a><span data-ttu-id="b22f6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b22f6-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="b22f6-107">實際： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b22f6-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b22f6-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="b22f6-108">The number to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="b22f6-109">預期： [複雜](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b22f6-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b22f6-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="b22f6-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b22f6-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b22f6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

