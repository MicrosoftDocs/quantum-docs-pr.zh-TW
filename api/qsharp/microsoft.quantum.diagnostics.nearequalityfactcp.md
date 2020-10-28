---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 1d62d25a3d04c431440cf8fc1eb585cac2c73f2e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698062"
---
# <a name="nearequalityfactcp-function"></a><span data-ttu-id="4c9ba-102">NearEqualityFactCP 函式</span><span class="sxs-lookup"><span data-stu-id="4c9ba-102">NearEqualityFactCP function</span></span>

<span data-ttu-id="4c9ba-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4c9ba-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4c9ba-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c9ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c9ba-105">判斷值，傳統複數的預期值最高可達 1e-10 的小容錯。</span><span class="sxs-lookup"><span data-stu-id="4c9ba-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a><span data-ttu-id="4c9ba-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4c9ba-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="4c9ba-107">實際： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="4c9ba-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="4c9ba-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="4c9ba-108">The number to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="4c9ba-109">預期： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="4c9ba-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="4c9ba-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="4c9ba-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4c9ba-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4c9ba-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

