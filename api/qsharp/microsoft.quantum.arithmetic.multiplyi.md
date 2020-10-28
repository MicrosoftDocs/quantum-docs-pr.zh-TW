---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: MultiplyI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699570"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="bbaa8-102">MultiplyI 操作</span><span class="sxs-lookup"><span data-stu-id="bbaa8-102">MultiplyI operation</span></span>

<span data-ttu-id="bbaa8-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bbaa8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bbaa8-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbaa8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbaa8-105">將整數乘以 `xs` 整數 `ys` 並將結果儲存在中 `result` ，這一開始必須是零。</span><span class="sxs-lookup"><span data-stu-id="bbaa8-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="bbaa8-106">輸入</span><span class="sxs-lookup"><span data-stu-id="bbaa8-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="bbaa8-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bbaa8-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bbaa8-108">$n $ bit 被乘數 (LittleEndian) </span><span class="sxs-lookup"><span data-stu-id="bbaa8-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="bbaa8-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bbaa8-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bbaa8-110">$n $ bit 乘數 (LittleEndian) </span><span class="sxs-lookup"><span data-stu-id="bbaa8-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="bbaa8-111">結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bbaa8-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bbaa8-112">$ 2n $ bit result (LittleEndian) ，必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="bbaa8-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bbaa8-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bbaa8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bbaa8-114">備註</span><span class="sxs-lookup"><span data-stu-id="bbaa8-114">Remarks</span></span>

<span data-ttu-id="bbaa8-115">使用標準的 shift 和 add 方法來執行乘法。</span><span class="sxs-lookup"><span data-stu-id="bbaa8-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="bbaa8-116">藉由將 $x _i $ 複製到控制項量子位上的 ancilla 量子位，然後控制 ancilla 量子位的加法，來改善受控制版本。</span><span class="sxs-lookup"><span data-stu-id="bbaa8-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>