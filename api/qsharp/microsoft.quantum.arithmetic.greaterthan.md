---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 644d68affbdb508938f76de5025a1a463e7284e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223080"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="a6dcf-102">GreaterThan 操作</span><span class="sxs-lookup"><span data-stu-id="a6dcf-102">GreaterThan operation</span></span>

<span data-ttu-id="a6dcf-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a6dcf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a6dcf-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6dcf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6dcf-105">在編碼為量子位暫存器的兩個整數之間套用大於比較，並根據比較結果來翻轉目標量子位。</span><span class="sxs-lookup"><span data-stu-id="a6dcf-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a6dcf-106">描述</span><span class="sxs-lookup"><span data-stu-id="a6dcf-106">Description</span></span>

<span data-ttu-id="a6dcf-107">執行嚴格大於兩個整數 $x $ 和 $y $ 的比較，在量子位中編碼的是 xs 和 y) 。</span><span class="sxs-lookup"><span data-stu-id="a6dcf-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="a6dcf-108">如果 $x > y $，則結果量子位將會翻轉，否則結果量子位將會保留其狀態。</span><span class="sxs-lookup"><span data-stu-id="a6dcf-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="a6dcf-109">輸入</span><span class="sxs-lookup"><span data-stu-id="a6dcf-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a6dcf-110">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a6dcf-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a6dcf-111">LittleEndian 量子位會將第一個整數的編碼編碼 $x $。</span><span class="sxs-lookup"><span data-stu-id="a6dcf-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a6dcf-112">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a6dcf-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a6dcf-113">LittleEndian 量子位會將第二個整數的編碼 $y $。</span><span class="sxs-lookup"><span data-stu-id="a6dcf-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="a6dcf-114">結果： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a6dcf-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a6dcf-115">如果 $x > y $，將會翻轉的單一量子位。</span><span class="sxs-lookup"><span data-stu-id="a6dcf-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6dcf-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6dcf-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a6dcf-117">備註</span><span class="sxs-lookup"><span data-stu-id="a6dcf-117">Remarks</span></span>

<span data-ttu-id="a6dcf-118">使用 $x-y = (x ' + y) ' $ 的訣竅，其中 ' 代表一補數。</span><span class="sxs-lookup"><span data-stu-id="a6dcf-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="a6dcf-119">參考</span><span class="sxs-lookup"><span data-stu-id="a6dcf-119">References</span></span>

- <span data-ttu-id="a6dcf-120">Steven Cuccaro、Thomas g. Draper、Samuel A. Kutin、David Petrie Moulton：「新的量子 ripple-攜帶加法電路」、2004。</span><span class="sxs-lookup"><span data-stu-id="a6dcf-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="a6dcf-121">Thomas Haener，聖馬丁 Roetteler，Krysta M. Svore： "使用 2n + 2 量子位搭配 Toffoli 型模組化乘法進行分解"，2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="a6dcf-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>