---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699899"
---
# <a name="dividei-operation"></a><span data-ttu-id="83326-102">DivideI 操作</span><span class="sxs-lookup"><span data-stu-id="83326-102">DivideI operation</span></span>

<span data-ttu-id="83326-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="83326-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="83326-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83326-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83326-105">將兩個量子整數相除。</span><span class="sxs-lookup"><span data-stu-id="83326-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="83326-106">描述</span><span class="sxs-lookup"><span data-stu-id="83326-106">Description</span></span>

<span data-ttu-id="83326-107">`xs` 將保留其餘部分 `xs - floor(xs/ys) * ys` ，並 `result` 將保留 `floor(xs/ys)` 。</span><span class="sxs-lookup"><span data-stu-id="83326-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="83326-108">輸入</span><span class="sxs-lookup"><span data-stu-id="83326-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="83326-109">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="83326-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="83326-110">$n $ 位被除數，將被餘數取代。</span><span class="sxs-lookup"><span data-stu-id="83326-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="83326-111">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="83326-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="83326-112">$n $ bit 除數</span><span class="sxs-lookup"><span data-stu-id="83326-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="83326-113">結果： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="83326-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="83326-114">$n $ bit 結果時，必須先處於狀態 $ \ket {0} $，並且將由整數除法的結果取代。</span><span class="sxs-lookup"><span data-stu-id="83326-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="83326-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83326-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="83326-116">備註</span><span class="sxs-lookup"><span data-stu-id="83326-116">Remarks</span></span>

<span data-ttu-id="83326-117">使用標準的 shift 和減法方法來執行除法。</span><span class="sxs-lookup"><span data-stu-id="83326-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="83326-118">受控制的版本是特製化的，因此減法不需要額外的控制項。</span><span class="sxs-lookup"><span data-stu-id="83326-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>