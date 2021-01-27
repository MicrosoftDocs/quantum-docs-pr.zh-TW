---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: MultiplexOperationsFromGenerator 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 59afa9d9a34fe74206118680940d243ed8b2496e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852502"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="41ff3-102">MultiplexOperationsFromGenerator 操作</span><span class="sxs-lookup"><span data-stu-id="41ff3-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="41ff3-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41ff3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41ff3-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41ff3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41ff3-105">套用 $U $ 的乘法控制項單一作業，此作業會在由 n-量子位 number state $ \ket{j} $ 控制時套用單一 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="41ff3-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="41ff3-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="41ff3-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="41ff3-107">輸入</span><span class="sxs-lookup"><span data-stu-id="41ff3-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="41ff3-108">unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int) -> t => [單位](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="41ff3-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="41ff3-109">元組，其中第一個專案 `Int` 是 unitaries $N $ 的數目，而第二個元素 `(Int -> ('T => () is Adj + Ctl))` 是採用整數 $j $ in $ [0，n-1] $ 的函式，並輸出單一作業 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="41ff3-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="41ff3-110">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="41ff3-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="41ff3-111">以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="41ff3-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="41ff3-112">目標： t</span><span class="sxs-lookup"><span data-stu-id="41ff3-112">target : 'T</span></span>

<span data-ttu-id="41ff3-113">$V _j $ 的一般量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="41ff3-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41ff3-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41ff3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="41ff3-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="41ff3-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41ff3-116">不要</span><span class="sxs-lookup"><span data-stu-id="41ff3-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="41ff3-117">備註</span><span class="sxs-lookup"><span data-stu-id="41ff3-117">Remarks</span></span>

<span data-ttu-id="41ff3-118">`coefficients` 如果指定了少於 $ 2 ^ n $，將會以識別元素填補。</span><span class="sxs-lookup"><span data-stu-id="41ff3-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="41ff3-119">此實行使用 $n-$1 輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="41ff3-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="41ff3-120">參考資料</span><span class="sxs-lookup"><span data-stu-id="41ff3-120">References</span></span>

- [<span data-ttu-id="41ff3-121">*Andrew M. Childs、Dmitri Maslov、Yunseong 等、Neil J. Ross、中國人民幣 Su*、arXiv：1711.10980</span><span class="sxs-lookup"><span data-stu-id="41ff3-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su*, arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)