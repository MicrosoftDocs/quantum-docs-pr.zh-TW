---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: 48d3cd3d5f6aea265fac2f50b913ab855a31accf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697931"
---
# <a name="recovercss-operation"></a><span data-ttu-id="e12e7-102">RecoverCSS 操作</span><span class="sxs-lookup"><span data-stu-id="e12e7-102">RecoverCSS operation</span></span>

<span data-ttu-id="e12e7-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e12e7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e12e7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e12e7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e12e7-105">依類型所描述的量副程式代碼，執行單次錯誤修正 `CSS` 。</span><span class="sxs-lookup"><span data-stu-id="e12e7-105">Performs a single round of error correction by a quantum code described by a `CSS` type.</span></span>

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="e12e7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e12e7-106">Input</span></span>

### <a name="code--css"></a><span data-ttu-id="e12e7-107">程式碼： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="e12e7-107">code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="e12e7-108">封裝為類型的量子 CSS 錯誤修正程式碼 `CSS` 會描述量子資料的編碼和解碼，以及如何測量錯誤 syndromes。</span><span class="sxs-lookup"><span data-stu-id="e12e7-108">A quantum CSS error-correcting code packaged as a `CSS` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fnx--recoveryfn"></a><span data-ttu-id="e12e7-109">fnX： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="e12e7-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="e12e7-110">`RecoveryFn`，會將每個 $X $ 錯誤的症狀對應到可 `Pauli[]` 更正偵測到之錯誤的作業。</span><span class="sxs-lookup"><span data-stu-id="e12e7-110">A `RecoveryFn` that maps each $X$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="fnz--recoveryfn"></a><span data-ttu-id="e12e7-111">fnZ： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="e12e7-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="e12e7-112">`RecoveryFn`，會將每個 $Z $ 錯誤的症狀對應到可 `Pauli[]` 更正偵測到之錯誤的作業。</span><span class="sxs-lookup"><span data-stu-id="e12e7-112">A `RecoveryFn` that maps each $Z$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="e12e7-113">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="e12e7-113">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="e12e7-114">定義了穩定程式碼的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="e12e7-114">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e12e7-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e12e7-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e12e7-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e12e7-116">See Also</span></span>

- [<span data-ttu-id="e12e7-117">ErrorCorrection .CSS</span><span class="sxs-lookup"><span data-stu-id="e12e7-117">Microsoft.Quantum.ErrorCorrection.CSS</span></span>](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [<span data-ttu-id="e12e7-118">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="e12e7-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="e12e7-119">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="e12e7-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)