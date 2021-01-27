---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855571"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="46532-102">ApplyTransposition 操作</span><span class="sxs-lookup"><span data-stu-id="46532-102">ApplyTransposition operation</span></span>

<span data-ttu-id="46532-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="46532-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="46532-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46532-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="46532-105">描述</span><span class="sxs-lookup"><span data-stu-id="46532-105">Description</span></span>

<span data-ttu-id="46532-106">這項作業會以指定的 `a` `b` 狀態向量（長度為 $n $），將索引中的波幅交換至索引的波幅 `register` 。</span><span class="sxs-lookup"><span data-stu-id="46532-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="46532-107">如果 `a` 等於 `b` ，則不會變更狀態向量。</span><span class="sxs-lookup"><span data-stu-id="46532-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="46532-108">輸入</span><span class="sxs-lookup"><span data-stu-id="46532-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="46532-109">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46532-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46532-110">第一個索引 (必須是介於0到 $ 2 ^ n-$1 之間的值) </span><span class="sxs-lookup"><span data-stu-id="46532-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="46532-111">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46532-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46532-112">第二個索引 (必須是介於0到 $ 2 ^ n-$1 之間的值) </span><span class="sxs-lookup"><span data-stu-id="46532-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="46532-113">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="46532-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="46532-114">要套用調換的 $n $ 量子位清單。</span><span class="sxs-lookup"><span data-stu-id="46532-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46532-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46532-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="46532-116">範例</span><span class="sxs-lookup"><span data-stu-id="46532-116">Example</span></span>

<span data-ttu-id="46532-117">在2量子位上準備數位狀態 $ | 1 \ rangle $、$ | 2 \ rangle $ 和 $ | 3 \ rangle $ 的統一迭加。</span><span class="sxs-lookup"><span data-stu-id="46532-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```