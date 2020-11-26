---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 95364541adfa1dc57b1f147c3992c9fd9f5f6c68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201558"
---
# <a name="nearequalityfactcp-function"></a><span data-ttu-id="b63ed-102">NearEqualityFactCP 函式</span><span class="sxs-lookup"><span data-stu-id="b63ed-102">NearEqualityFactCP function</span></span>

<span data-ttu-id="b63ed-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b63ed-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b63ed-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b63ed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b63ed-105">判斷值，傳統複數的預期值最高可達 1e-10 的小容錯。</span><span class="sxs-lookup"><span data-stu-id="b63ed-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a><span data-ttu-id="b63ed-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b63ed-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="b63ed-107">實際： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="b63ed-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="b63ed-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="b63ed-108">The number to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="b63ed-109">預期： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="b63ed-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="b63ed-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="b63ed-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b63ed-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b63ed-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

