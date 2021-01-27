---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843736"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="72002-102">ApplyMajorityInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="72002-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="72002-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="72002-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="72002-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72002-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72002-105">在量子位的註冊上就地套用三個量子位的多數作業。</span><span class="sxs-lookup"><span data-stu-id="72002-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="72002-106">描述</span><span class="sxs-lookup"><span data-stu-id="72002-106">Description</span></span>

<span data-ttu-id="72002-107">這項作業會在3量子位上就地計算多數函數。</span><span class="sxs-lookup"><span data-stu-id="72002-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="72002-108">如果我們將輸出量子位表示為 $x $ 和 $y $ 的 $z $ 和輸入量子位，則作業會執行下列轉換： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x，y，z) } $。</span><span class="sxs-lookup"><span data-stu-id="72002-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="72002-109">輸入</span><span class="sxs-lookup"><span data-stu-id="72002-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="72002-110">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="72002-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="72002-111">第一個輸入量子位。</span><span class="sxs-lookup"><span data-stu-id="72002-111">First input qubit.</span></span> <span data-ttu-id="72002-112">請注意，輸出會就地計算並儲存在此量子位中。</span><span class="sxs-lookup"><span data-stu-id="72002-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="72002-113">輸入： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="72002-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="72002-114">第二個和第三個輸入量子位。</span><span class="sxs-lookup"><span data-stu-id="72002-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72002-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72002-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

