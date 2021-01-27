---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: RippleCarryAdderD 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: f0f6f39fbff9f682f8f74a982c0a41847df1397a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842956"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="bd082-102">RippleCarryAdderD 操作</span><span class="sxs-lookup"><span data-stu-id="bd082-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="bd082-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bd082-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bd082-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd082-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd082-105">可還原的就地 ripple-包含兩個整數的加法。</span><span class="sxs-lookup"><span data-stu-id="bd082-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="bd082-106">假設有兩個 $n $ bit 整數編碼在 LittleEndian 暫存器中 `xs` `ys` ，而且量子位包含，則作業會計算兩個整數的總和，其中會保留結果的 $n $ 最低有效位數 `ys` ，而執行時位會進行 xor 至量子位 `carry` 。</span><span class="sxs-lookup"><span data-stu-id="bd082-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bd082-107">輸入</span><span class="sxs-lookup"><span data-stu-id="bd082-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="bd082-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bd082-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bd082-109">LittleEndian 量子位登錄第一個整數被加數的編碼。</span><span class="sxs-lookup"><span data-stu-id="bd082-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="bd082-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bd082-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bd082-111">LittleEndian 量子位暫存器第二個整數被加數的編碼，會修改成保存總和的 $n $ 最不重要的位。</span><span class="sxs-lookup"><span data-stu-id="bd082-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="bd082-112">攜帶： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bd082-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bd082-113">帶有量子位，是以總和的最高有效位進行 xor。</span><span class="sxs-lookup"><span data-stu-id="bd082-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bd082-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd082-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bd082-115">備註</span><span class="sxs-lookup"><span data-stu-id="bd082-115">Remarks</span></span>

<span data-ttu-id="bd082-116">指定的受控制作業會使用作業的對稱和相互取消，以改善將控制項加入至每個作業的預設執行。</span><span class="sxs-lookup"><span data-stu-id="bd082-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="bd082-117">參考資料</span><span class="sxs-lookup"><span data-stu-id="bd082-117">References</span></span>

- <span data-ttu-id="bd082-118">Thomas g. Draper：「在量子電腦上新增」，2000。</span><span class="sxs-lookup"><span data-stu-id="bd082-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033