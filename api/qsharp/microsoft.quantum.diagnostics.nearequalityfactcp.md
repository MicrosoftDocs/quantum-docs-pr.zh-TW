---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 477449913732950ad26adc0cdabaaaab803a20c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853274"
---
# <a name="nearequalityfactcp-function"></a><span data-ttu-id="422ae-102">NearEqualityFactCP 函式</span><span class="sxs-lookup"><span data-stu-id="422ae-102">NearEqualityFactCP function</span></span>

<span data-ttu-id="422ae-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="422ae-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="422ae-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="422ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="422ae-105">判斷值，傳統複數的預期值最高可達 1e-10 的小容錯。</span><span class="sxs-lookup"><span data-stu-id="422ae-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a><span data-ttu-id="422ae-106">輸入</span><span class="sxs-lookup"><span data-stu-id="422ae-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="422ae-107">實際： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="422ae-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="422ae-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="422ae-108">The number to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="422ae-109">預期： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="422ae-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="422ae-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="422ae-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="422ae-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="422ae-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

