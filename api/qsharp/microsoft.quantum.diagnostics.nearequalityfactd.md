---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827899"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="d3e39-102">NearEqualityFactD 函式</span><span class="sxs-lookup"><span data-stu-id="d3e39-102">NearEqualityFactD function</span></span>

<span data-ttu-id="d3e39-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d3e39-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d3e39-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3e39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3e39-105">判斷值，傳統浮點值的預期值最高可達 1e-10 的小容錯。</span><span class="sxs-lookup"><span data-stu-id="d3e39-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="d3e39-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d3e39-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="d3e39-107">實際： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3e39-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3e39-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="d3e39-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="d3e39-109">預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d3e39-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d3e39-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="d3e39-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3e39-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3e39-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d3e39-112">備註</span><span class="sxs-lookup"><span data-stu-id="d3e39-112">Remarks</span></span>

<span data-ttu-id="d3e39-113">這相當於 <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> 具有 $10 ^ $ 的硬式編碼容錯 {-10} 。</span><span class="sxs-lookup"><span data-stu-id="d3e39-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>