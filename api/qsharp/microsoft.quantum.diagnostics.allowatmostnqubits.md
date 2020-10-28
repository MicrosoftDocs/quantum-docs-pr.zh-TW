---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698175"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="7dbf1-102">AllowAtMostNQubits 操作</span><span class="sxs-lookup"><span data-stu-id="7dbf1-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="7dbf1-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7dbf1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7dbf1-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7dbf1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7dbf1-105">在呼叫此作業和其 adjoint 之間，判斷最多可使用語句來配置指定數目的其他量子位。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7dbf1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7dbf1-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="7dbf1-107">nQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7dbf1-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7dbf1-108">可能配置的量子位數目上限。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="7dbf1-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7dbf1-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7dbf1-110">失敗時要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7dbf1-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7dbf1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7dbf1-112">備註</span><span class="sxs-lookup"><span data-stu-id="7dbf1-112">Remarks</span></span>

<span data-ttu-id="7dbf1-113">在不支援此作業的目標上，此作業可能會取代為無作業。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>