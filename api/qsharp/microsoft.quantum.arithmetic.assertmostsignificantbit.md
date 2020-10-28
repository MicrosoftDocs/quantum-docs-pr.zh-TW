---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699954"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="3b47c-102">AssertMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="3b47c-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="3b47c-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3b47c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3b47c-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b47c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b47c-105">判斷提示代表不帶正負號的整數之量子位暫存器最重要的量子位處於特定狀態。</span><span class="sxs-lookup"><span data-stu-id="3b47c-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="3b47c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3b47c-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="3b47c-107">值： __無效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3b47c-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="3b47c-108">要判斷提示的最高位值。</span><span class="sxs-lookup"><span data-stu-id="3b47c-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="3b47c-109">編號： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3b47c-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3b47c-110">檢查最大位的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="3b47c-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b47c-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b47c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3b47c-112">備註</span><span class="sxs-lookup"><span data-stu-id="3b47c-112">Remarks</span></span>

<span data-ttu-id="3b47c-113">此操作的受控制版本會忽略控制項。</span><span class="sxs-lookup"><span data-stu-id="3b47c-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b47c-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3b47c-114">See Also</span></span>

- [<span data-ttu-id="3b47c-115">... Assert</span><span class="sxs-lookup"><span data-stu-id="3b47c-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)