---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843415"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="3e88f-102">AssertMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="3e88f-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="3e88f-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3e88f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3e88f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3e88f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3e88f-105">判斷提示代表不帶正負號的整數之量子位暫存器最重要的量子位處於特定狀態。</span><span class="sxs-lookup"><span data-stu-id="3e88f-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3e88f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3e88f-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="3e88f-107">值：__無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3e88f-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="3e88f-108">要判斷提示的最高位值。</span><span class="sxs-lookup"><span data-stu-id="3e88f-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="3e88f-109">編號： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3e88f-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3e88f-110">檢查最大位的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="3e88f-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e88f-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e88f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3e88f-112">備註</span><span class="sxs-lookup"><span data-stu-id="3e88f-112">Remarks</span></span>

<span data-ttu-id="3e88f-113">此操作的受控制版本會忽略控制項。</span><span class="sxs-lookup"><span data-stu-id="3e88f-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e88f-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3e88f-114">See Also</span></span>

- [<span data-ttu-id="3e88f-115">... Assert</span><span class="sxs-lookup"><span data-stu-id="3e88f-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)