---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: 復原操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: 3e2ce404ae3a6b4097897b859388fea3f915232c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825513"
---
# <a name="recover-operation"></a><span data-ttu-id="a60cd-102">復原操作</span><span class="sxs-lookup"><span data-stu-id="a60cd-102">Recover operation</span></span>

<span data-ttu-id="a60cd-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a60cd-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a60cd-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a60cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a60cd-105">依類型所描述的量副程式代碼，執行單次錯誤修正 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="a60cd-105">Performs a single round of error correction by a quantum code described by a `QECC` type.</span></span>

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="a60cd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="a60cd-106">Input</span></span>

### <a name="code--qecc"></a><span data-ttu-id="a60cd-107">程式碼： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="a60cd-107">code : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="a60cd-108">封裝為類型的量子錯誤修正程式碼 `QECC` 會描述量子資料的編碼和解碼，以及如何測量錯誤 syndromes。</span><span class="sxs-lookup"><span data-stu-id="a60cd-108">A quantum error-correcting code packaged as a `QECC` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fn--recoveryfn"></a><span data-ttu-id="a60cd-109">fn： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="a60cd-109">fn : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="a60cd-110">`RecoveryFn`，會將每個錯誤的症狀對應到可 `Pauli[]` 更正偵測到之錯誤的作業。</span><span class="sxs-lookup"><span data-stu-id="a60cd-110">A `RecoveryFn` that maps each error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="a60cd-111">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="a60cd-111">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="a60cd-112">定義了穩定程式碼的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="a60cd-112">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a60cd-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a60cd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a60cd-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a60cd-114">See Also</span></span>

- [<span data-ttu-id="a60cd-115">ErrorCorrection. QECC</span><span class="sxs-lookup"><span data-stu-id="a60cd-115">Microsoft.Quantum.ErrorCorrection.QECC</span></span>](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [<span data-ttu-id="a60cd-116">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="a60cd-116">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="a60cd-117">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="a60cd-117">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)