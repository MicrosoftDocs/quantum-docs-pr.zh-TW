---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830903"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="211f0-102">AllowAtMostNQubits 操作</span><span class="sxs-lookup"><span data-stu-id="211f0-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="211f0-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="211f0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="211f0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="211f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="211f0-105">在呼叫此作業和其 adjoint 之間，判斷最多可使用語句來配置指定數目的其他量子位。</span><span class="sxs-lookup"><span data-stu-id="211f0-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="211f0-106">輸入</span><span class="sxs-lookup"><span data-stu-id="211f0-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="211f0-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="211f0-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="211f0-108">可能配置的量子位數目上限。</span><span class="sxs-lookup"><span data-stu-id="211f0-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="211f0-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="211f0-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="211f0-110">失敗時要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="211f0-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="211f0-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="211f0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="211f0-112">範例</span><span class="sxs-lookup"><span data-stu-id="211f0-112">Example</span></span>

<span data-ttu-id="211f0-113">下列程式碼片段在支援此診斷的電腦上執行時，將會失敗：</span><span class="sxs-lookup"><span data-stu-id="211f0-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="211f0-114">備註</span><span class="sxs-lookup"><span data-stu-id="211f0-114">Remarks</span></span>

<span data-ttu-id="211f0-115">在不支援此作業的目標上，此作業可能會取代為無作業。</span><span class="sxs-lookup"><span data-stu-id="211f0-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>