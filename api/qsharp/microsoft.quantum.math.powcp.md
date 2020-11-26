---
uid: Microsoft.Quantum.Math.PowCP
title: PowCP 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowCP
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 185d40acff6027a775130faaff64582c58384a90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194639"
---
# <a name="powcp-function"></a><span data-ttu-id="1cb6a-102">PowCP 函式</span><span class="sxs-lookup"><span data-stu-id="1cb6a-102">PowCP function</span></span>

<span data-ttu-id="1cb6a-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1cb6a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1cb6a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1cb6a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1cb6a-105">傳回指定乘冪的數位。</span><span class="sxs-lookup"><span data-stu-id="1cb6a-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowCP (a : Microsoft.Quantum.Math.ComplexPolar, power : Microsoft.Quantum.Math.ComplexPolar) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="1cb6a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1cb6a-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="1cb6a-107">答： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1cb6a-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1cb6a-108">要引發 $a $ 的數位。</span><span class="sxs-lookup"><span data-stu-id="1cb6a-108">The number $a$ that is to be raised.</span></span>


### <a name="power--complexpolar"></a><span data-ttu-id="1cb6a-109">電源： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1cb6a-109">power : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1cb6a-110">應該引發 $a $ 的 power $b $。</span><span class="sxs-lookup"><span data-stu-id="1cb6a-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--complexpolar"></a><span data-ttu-id="1cb6a-111">輸出： [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1cb6a-111">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1cb6a-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="1cb6a-112">The power $a^b$</span></span>