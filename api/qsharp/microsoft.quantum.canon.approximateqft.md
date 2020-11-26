---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 97a410133e80cc5bffc810e9d6455baaee32364b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207695"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="e6da9-102">ApproximateQFT 操作</span><span class="sxs-lookup"><span data-stu-id="e6da9-102">ApproximateQFT operation</span></span>

<span data-ttu-id="e6da9-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e6da9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e6da9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6da9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6da9-105">將大約的量子傅立葉轉換 (AQFT) 套用至量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="e6da9-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e6da9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e6da9-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e6da9-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e6da9-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e6da9-108">近似值參數，決定 QFT 電路中所發生之受控制 Z 旋轉的水準剪除。</span><span class="sxs-lookup"><span data-stu-id="e6da9-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="e6da9-109">近似值參數 a 決定 Z 旋轉的剪除層級，亦即，∈ {0 ... n} 和所有 Z 旋轉2π/2k，其中 k>a 會從 QFT 電路中移除。</span><span class="sxs-lookup"><span data-stu-id="e6da9-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="e6da9-110">已知 >= log ₂ (n) + log ₂ (1/ε) + 3 1 可以系結 | |QFT-AQFT | |<ε。</span><span class="sxs-lookup"><span data-stu-id="e6da9-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="e6da9-111">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="e6da9-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="e6da9-112">套用近似量子傅立葉轉換之 n 量子位的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="e6da9-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e6da9-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6da9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e6da9-114">備註</span><span class="sxs-lookup"><span data-stu-id="e6da9-114">Remarks</span></span>

<span data-ttu-id="e6da9-115">AQFT 需要2π/2k 和 Hadamard 閘道格式的 Z 旋轉閘道。</span><span class="sxs-lookup"><span data-stu-id="e6da9-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="e6da9-116">輸入和輸出會假設以位元組由大到小的編碼方式進行編碼。</span><span class="sxs-lookup"><span data-stu-id="e6da9-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="e6da9-117">參考</span><span class="sxs-lookup"><span data-stu-id="e6da9-117">References</span></span>

- [<span data-ttu-id="e6da9-118">*Roetteler，Beth*，Appl.exe. Commun。電腦.19 (3) ： 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="e6da9-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="e6da9-119">*D. Coppersmith* arXiv： quant-ph/0201067v1</span><span class="sxs-lookup"><span data-stu-id="e6da9-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)