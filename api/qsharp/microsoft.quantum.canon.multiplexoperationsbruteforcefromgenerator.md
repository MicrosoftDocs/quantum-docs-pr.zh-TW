---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: a700cffbd8fe8be01fdb7344cc9d4b02a4900174
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205995"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="8ad6c-102">MultiplexOperationsBruteForceFromGenerator 操作</span><span class="sxs-lookup"><span data-stu-id="8ad6c-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="8ad6c-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8ad6c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8ad6c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ad6c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8ad6c-105">適用于 $U $ 的乘法控制項單一作業，可在由 n 量子位 number state $ \ket{j} $ 控制時套用單一 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="8ad6c-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="8ad6c-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="8ad6c-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8ad6c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="8ad6c-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="8ad6c-108">unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[Int](xref:microsoft.quantum.lang-ref.int) -> t => [單位](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl) </span><span class="sxs-lookup"><span data-stu-id="8ad6c-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="8ad6c-109">元組，其中第一個專案 `Int` 是 unitaries $N $ 的數目，而第二個元素 `(Int -> ('T => () is Adj + Ctl))` 是採用整數 $j $ in $ [0，n-1] $ 的函式，並輸出單一作業 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="8ad6c-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="8ad6c-110">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8ad6c-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8ad6c-111">以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="8ad6c-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="8ad6c-112">目標： t</span><span class="sxs-lookup"><span data-stu-id="8ad6c-112">target : 'T</span></span>

<span data-ttu-id="8ad6c-113">$V _j $ 的一般量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="8ad6c-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ad6c-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ad6c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8ad6c-115">類型參數</span><span class="sxs-lookup"><span data-stu-id="8ad6c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8ad6c-116">不要</span><span class="sxs-lookup"><span data-stu-id="8ad6c-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="8ad6c-117">備註</span><span class="sxs-lookup"><span data-stu-id="8ad6c-117">Remarks</span></span>

<span data-ttu-id="8ad6c-118">`coefficients` 如果指定了少於 $ 2 ^ n $，將會以識別元素填補。</span><span class="sxs-lookup"><span data-stu-id="8ad6c-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="8ad6c-119">此版本是直接透過透過 n 個控制的單一運算子來執行。</span><span class="sxs-lookup"><span data-stu-id="8ad6c-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>