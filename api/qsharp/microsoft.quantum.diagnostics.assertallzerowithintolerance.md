---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698171"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="12e9e-102">AssertAllZeroWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="12e9e-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="12e9e-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="12e9e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="12e9e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12e9e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12e9e-105">判斷提示，指定的量子位全都在 $ \ket {0} $ 狀態中，直到指定的容錯。</span><span class="sxs-lookup"><span data-stu-id="12e9e-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="12e9e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="12e9e-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="12e9e-107">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="12e9e-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="12e9e-108">判斷提示為 $ \ket $ 狀態的量子位 {0} 。</span><span class="sxs-lookup"><span data-stu-id="12e9e-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="12e9e-109">容錯： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="12e9e-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="12e9e-110">狀態應該處於 $ \ket {0} $ state 的精確度</span><span class="sxs-lookup"><span data-stu-id="12e9e-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="12e9e-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="12e9e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="12e9e-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="12e9e-112">See Also</span></span>

- [<span data-ttu-id="12e9e-113">AssertQubitWithinTolerance。</span><span class="sxs-lookup"><span data-stu-id="12e9e-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)