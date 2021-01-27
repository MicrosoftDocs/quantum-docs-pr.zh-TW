---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828758"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="9fde9-102">EqualityWithinToleranceFact 函式</span><span class="sxs-lookup"><span data-stu-id="9fde9-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="9fde9-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9fde9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9fde9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fde9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fde9-105">表示傳統浮點數值的預期值為指定絕對容錯值的宣告。</span><span class="sxs-lookup"><span data-stu-id="9fde9-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="9fde9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9fde9-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="9fde9-107">實際： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9fde9-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9fde9-108">要檢查的數位。</span><span class="sxs-lookup"><span data-stu-id="9fde9-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="9fde9-109">預期： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9fde9-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9fde9-110">預期的值。</span><span class="sxs-lookup"><span data-stu-id="9fde9-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="9fde9-111">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9fde9-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9fde9-112">實際和預期之間差異的絕對容錯。</span><span class="sxs-lookup"><span data-stu-id="9fde9-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9fde9-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9fde9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

