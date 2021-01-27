---
uid: Microsoft.Quantum.Math.PowL
title: PowL 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: f7282a3639ca87dae731e39594576aa73c4602ac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857454"
---
# <a name="powl-function"></a><span data-ttu-id="70ba8-102">PowL 函式</span><span class="sxs-lookup"><span data-stu-id="70ba8-102">PowL function</span></span>

<span data-ttu-id="70ba8-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="70ba8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="70ba8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70ba8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70ba8-105">傳回指定乘冪的數位。</span><span class="sxs-lookup"><span data-stu-id="70ba8-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="70ba8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="70ba8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="70ba8-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="70ba8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="70ba8-108">要引發 $a $ 的數位。</span><span class="sxs-lookup"><span data-stu-id="70ba8-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="70ba8-109">電源： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="70ba8-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="70ba8-110">應該引發 $a $ 的 power $b $。</span><span class="sxs-lookup"><span data-stu-id="70ba8-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="70ba8-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="70ba8-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="70ba8-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="70ba8-112">The power $a^b$</span></span>