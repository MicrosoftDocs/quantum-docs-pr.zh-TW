---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846692"
---
# <a name="dividei-operation"></a><span data-ttu-id="a9519-102">DivideI 操作</span><span class="sxs-lookup"><span data-stu-id="a9519-102">DivideI operation</span></span>

<span data-ttu-id="a9519-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a9519-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a9519-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a9519-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a9519-105">將兩個量子整數相除。</span><span class="sxs-lookup"><span data-stu-id="a9519-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a9519-106">描述</span><span class="sxs-lookup"><span data-stu-id="a9519-106">Description</span></span>

<span data-ttu-id="a9519-107">`xs` 將保留其餘部分 `xs - floor(xs/ys) * ys` ，並 `result` 將保留 `floor(xs/ys)` 。</span><span class="sxs-lookup"><span data-stu-id="a9519-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="a9519-108">輸入</span><span class="sxs-lookup"><span data-stu-id="a9519-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a9519-109">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9519-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a9519-110">$n $ 位被除數，將被餘數取代。</span><span class="sxs-lookup"><span data-stu-id="a9519-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a9519-111">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9519-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a9519-112">$n $ bit 除數</span><span class="sxs-lookup"><span data-stu-id="a9519-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="a9519-113">結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9519-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a9519-114">$n $ bit 結果時，必須先處於狀態 $ \ket {0} $，並且將由整數除法的結果取代。</span><span class="sxs-lookup"><span data-stu-id="a9519-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9519-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9519-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a9519-116">備註</span><span class="sxs-lookup"><span data-stu-id="a9519-116">Remarks</span></span>

<span data-ttu-id="a9519-117">使用標準的 shift 和減法方法來執行除法。</span><span class="sxs-lookup"><span data-stu-id="a9519-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="a9519-118">受控制的版本是特製化的，因此減法不需要額外的控制項。</span><span class="sxs-lookup"><span data-stu-id="a9519-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>