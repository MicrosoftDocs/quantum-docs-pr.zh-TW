---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202544"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="5c209-102">AllowAtMostNQubits 操作</span><span class="sxs-lookup"><span data-stu-id="5c209-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="5c209-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5c209-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5c209-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c209-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c209-105">在呼叫此作業和其 adjoint 之間，判斷最多可使用語句來配置指定數目的其他量子位。</span><span class="sxs-lookup"><span data-stu-id="5c209-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5c209-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5c209-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="5c209-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c209-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c209-108">可能配置的量子位數目上限。</span><span class="sxs-lookup"><span data-stu-id="5c209-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="5c209-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5c209-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="5c209-110">失敗時要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="5c209-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c209-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c209-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5c209-112">備註</span><span class="sxs-lookup"><span data-stu-id="5c209-112">Remarks</span></span>

<span data-ttu-id="5c209-113">在不支援此作業的目標上，此作業可能會取代為無作業。</span><span class="sxs-lookup"><span data-stu-id="5c209-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>