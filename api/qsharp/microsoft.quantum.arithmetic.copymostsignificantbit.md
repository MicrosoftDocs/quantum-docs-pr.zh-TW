---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223284"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="ca72f-102">CopyMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="ca72f-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="ca72f-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ca72f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ca72f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca72f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca72f-105">將代表不帶正負號整數的量子位暫存器最重要的位複製 `from` 到量子位中 `target` 。</span><span class="sxs-lookup"><span data-stu-id="ca72f-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ca72f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ca72f-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="ca72f-107">來源： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ca72f-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ca72f-108">從中複製最大位的不帶正負號整數。</span><span class="sxs-lookup"><span data-stu-id="ca72f-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="ca72f-109">以位元組由小到大格式編碼的整數。</span><span class="sxs-lookup"><span data-stu-id="ca72f-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ca72f-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ca72f-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ca72f-111">要在其中複製最大位的量子位。</span><span class="sxs-lookup"><span data-stu-id="ca72f-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="ca72f-112">位編碼是以計算為基礎。</span><span class="sxs-lookup"><span data-stu-id="ca72f-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca72f-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca72f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ca72f-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ca72f-114">See Also</span></span>

- [<span data-ttu-id="ca72f-115">LittleEndian。</span><span class="sxs-lookup"><span data-stu-id="ca72f-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)