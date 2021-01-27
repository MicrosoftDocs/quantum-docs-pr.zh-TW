---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: RippleCarryAdderCDKM 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: df9b62b649af532a4202aacc3e8dd4613eb8665d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846369"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="e896a-102">RippleCarryAdderCDKM 操作</span><span class="sxs-lookup"><span data-stu-id="e896a-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="e896a-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e896a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e896a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e896a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e896a-105">可還原的就地 ripple-包含兩個整數的加法。</span><span class="sxs-lookup"><span data-stu-id="e896a-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e896a-106">描述</span><span class="sxs-lookup"><span data-stu-id="e896a-106">Description</span></span>

<span data-ttu-id="e896a-107">假設有兩個 $n $ bit 整數編碼在 LittleEndian 暫存器中 `xs` `ys` ，而且量子位包含，則作業會計算兩個整數的總和，其中會保留結果的 $n $ 最低有效位數 `ys` ，而執行時位會進行 xor 至量子位 `carry` 。</span><span class="sxs-lookup"><span data-stu-id="e896a-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="e896a-108">輸入</span><span class="sxs-lookup"><span data-stu-id="e896a-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e896a-109">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e896a-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e896a-110">LittleEndian 量子位登錄第一個整數被加數的編碼。</span><span class="sxs-lookup"><span data-stu-id="e896a-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e896a-111">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e896a-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e896a-112">LittleEndian 量子位暫存器第二個整數被加數的編碼，會修改為保留總和最少的 n 個最重要的位。</span><span class="sxs-lookup"><span data-stu-id="e896a-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="e896a-113">攜帶： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e896a-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e896a-114">帶有量子位，是以總和的最高有效位進行 xor。</span><span class="sxs-lookup"><span data-stu-id="e896a-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e896a-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e896a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e896a-116">備註</span><span class="sxs-lookup"><span data-stu-id="e896a-116">Remarks</span></span>

<span data-ttu-id="e896a-117">這項作業與 RippleCarryAdderD 具有相同的功能，但只會使用一個輔助量子位，而不是 $n $。</span><span class="sxs-lookup"><span data-stu-id="e896a-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="e896a-118">參考資料</span><span class="sxs-lookup"><span data-stu-id="e896a-118">References</span></span>

- <span data-ttu-id="e896a-119">Steven Cuccaro、Thomas g. Draper、Samuel A. Kutin、David Petrie Moulton：「新的量子 ripple-攜帶加法電路」、2004。</span><span class="sxs-lookup"><span data-stu-id="e896a-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1