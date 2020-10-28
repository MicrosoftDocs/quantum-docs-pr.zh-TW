---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700411"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="a1685-102">QuantumROMQubitCount 函式</span><span class="sxs-lookup"><span data-stu-id="a1685-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="a1685-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a1685-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a1685-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1685-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1685-105">傳回必須配置給所傳回之作業的量子位總數 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="a1685-105">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="a1685-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a1685-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="a1685-107">targetError： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1685-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a1685-108">目標錯誤 $ \epsilon $。</span><span class="sxs-lookup"><span data-stu-id="a1685-108">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="a1685-109">nCoeffs： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a1685-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a1685-110">中指定的係數數目 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="a1685-110">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="a1685-111">輸出： ([int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) # A3</span><span class="sxs-lookup"><span data-stu-id="a1685-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="a1685-112">第一個參數</span><span class="sxs-lookup"><span data-stu-id="a1685-112">First parameter</span></span>

<span data-ttu-id="a1685-113">元組， `(x,(y,z))` 其中 `x = y + z` 是配置的量子位總數， `y` 是註冊的量子位數目 `LittleEndian` ，而 `z` 是垃圾量子位的數目。</span><span class="sxs-lookup"><span data-stu-id="a1685-113">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>