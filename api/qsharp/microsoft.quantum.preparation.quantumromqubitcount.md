---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210398"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="959f1-102">QuantumROMQubitCount 函式</span><span class="sxs-lookup"><span data-stu-id="959f1-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="959f1-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="959f1-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="959f1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="959f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="959f1-105">QuantumROMQubitCount 已被取代。</span><span class="sxs-lookup"><span data-stu-id="959f1-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="959f1-106">請改用 <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements>。</span><span class="sxs-lookup"><span data-stu-id="959f1-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="959f1-107">傳回必須配置給所傳回之作業的量子位總數 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="959f1-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="959f1-108">輸入</span><span class="sxs-lookup"><span data-stu-id="959f1-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="959f1-109">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="959f1-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="959f1-110">目標錯誤 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="959f1-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="959f1-111">nCoeffs： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="959f1-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="959f1-112">中指定的係數數目 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="959f1-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="959f1-113">輸出： ([int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) # A3</span><span class="sxs-lookup"><span data-stu-id="959f1-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="959f1-114">第一個參數</span><span class="sxs-lookup"><span data-stu-id="959f1-114">First parameter</span></span>

<span data-ttu-id="959f1-115">元組， `(x,(y,z))` 其中 `x = y + z` 是配置的量子位總數， `y` 是註冊的量子位數目 `LittleEndian` ，而 `z` 是垃圾量子位的數目。</span><span class="sxs-lookup"><span data-stu-id="959f1-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>