---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 1cf483bb0d3b7cc43d271b65a2363fab95ff0f3b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852536"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="ebd8b-102">MultiplexOperations 操作</span><span class="sxs-lookup"><span data-stu-id="ebd8b-102">MultiplexOperations operation</span></span>

<span data-ttu-id="ebd8b-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ebd8b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ebd8b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebd8b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebd8b-105">套用由數位狀態陣列控制的作業陣列。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="ebd8b-106">亦即，套用由 $U $ 的乘法控制項單一作業，以 $n $-量子位 number state $ \ket{j} $ 控制時套用單一 $V _j $。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="ebd8b-107">$U = \sum ^ {2 ^ n-1-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ebd8b-108">輸入</span><span class="sxs-lookup"><span data-stu-id="ebd8b-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="ebd8b-109">unitaries： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="ebd8b-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="ebd8b-110">最多 $ 2 ^ n $ 單一作業的陣列。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="ebd8b-111">$J $ th 作業是由數位狀態 $ \ket{j} $ （以位元組由小到大格式編碼）來編制索引。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="ebd8b-112">index： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ebd8b-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ebd8b-113">以位元組由大到小的格式，$n $ 量子位 control register 編碼數位狀態 $ \ket{j} $。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="ebd8b-114">目標： t</span><span class="sxs-lookup"><span data-stu-id="ebd8b-114">target : 'T</span></span>

<span data-ttu-id="ebd8b-115">$V _j $ 的一般量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebd8b-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebd8b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ebd8b-117">類型參數</span><span class="sxs-lookup"><span data-stu-id="ebd8b-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ebd8b-118">不要</span><span class="sxs-lookup"><span data-stu-id="ebd8b-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="ebd8b-119">備註</span><span class="sxs-lookup"><span data-stu-id="ebd8b-119">Remarks</span></span>

<span data-ttu-id="ebd8b-120">`coefficients` 如果指定了少於 $ 2 ^ n $，將會以識別元素填補。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="ebd8b-121">此實行使用 $n-$1 輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="ebd8b-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="ebd8b-122">參考資料</span><span class="sxs-lookup"><span data-stu-id="ebd8b-122">References</span></span>

- <span data-ttu-id="ebd8b-123">使用量子的第一個量子模擬，Andrew M. Childs、Dmitri Maslov、Yunseong 等、Neil J. Ross、中國人民幣 Su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="ebd8b-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>