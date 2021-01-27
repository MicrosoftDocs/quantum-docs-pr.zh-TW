---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850330"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="9f48a-102">ApproximateQFT 操作</span><span class="sxs-lookup"><span data-stu-id="9f48a-102">ApproximateQFT operation</span></span>

<span data-ttu-id="9f48a-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9f48a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9f48a-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f48a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f48a-105">將大約的量子傅立葉轉換 (AQFT) 套用至量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="9f48a-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9f48a-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9f48a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9f48a-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f48a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f48a-108">近似值參數，決定 QFT 電路中所發生之受控制 Z 旋轉的水準剪除。</span><span class="sxs-lookup"><span data-stu-id="9f48a-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="9f48a-109">近似值參數 a 決定 Z 旋轉的剪除層級，亦即，∈ {0 ... n} 和所有 Z 旋轉2π/2k，其中 k>a 會從 QFT 電路中移除。</span><span class="sxs-lookup"><span data-stu-id="9f48a-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="9f48a-110">已知 >= log ₂ (n) + log ₂ (1/ε) + 3 1 可以系結 | |QFT-AQFT | |<ε。</span><span class="sxs-lookup"><span data-stu-id="9f48a-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="9f48a-111">qs： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="9f48a-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="9f48a-112">套用近似量子傅立葉轉換之 n 量子位的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="9f48a-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f48a-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f48a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9f48a-114">備註</span><span class="sxs-lookup"><span data-stu-id="9f48a-114">Remarks</span></span>

<span data-ttu-id="9f48a-115">AQFT 需要2π/2k 和 Hadamard 閘道格式的 Z 旋轉閘道。</span><span class="sxs-lookup"><span data-stu-id="9f48a-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="9f48a-116">輸入和輸出會假設以位元組由大到小的編碼方式進行編碼。</span><span class="sxs-lookup"><span data-stu-id="9f48a-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="9f48a-117">參考資料</span><span class="sxs-lookup"><span data-stu-id="9f48a-117">References</span></span>

- [<span data-ttu-id="9f48a-118">*Roetteler，Beth*，Appl.exe. Commun。電腦.19 (3) ： 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="9f48a-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="9f48a-119">*D. Coppersmith* arXiv： quant-ph/0201067v1</span><span class="sxs-lookup"><span data-stu-id="9f48a-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)