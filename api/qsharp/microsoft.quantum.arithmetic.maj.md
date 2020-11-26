---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 356689baa6d47b7b93a393f3672991bb589f6921
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222757"
---
# <a name="maj-operation"></a><span data-ttu-id="6e2a8-102">MAJ 操作</span><span class="sxs-lookup"><span data-stu-id="6e2a8-102">MAJ operation</span></span>

<span data-ttu-id="6e2a8-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6e2a8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6e2a8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e2a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e2a8-105">這會將就地操作的大部分作業套用至3量子位。</span><span class="sxs-lookup"><span data-stu-id="6e2a8-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6e2a8-106">描述</span><span class="sxs-lookup"><span data-stu-id="6e2a8-106">Description</span></span>

<span data-ttu-id="6e2a8-107">如果我們將目標量子位的狀態表示為 $ \ket{z} $，而輸入量子位的輸入狀態為 $ \ket{x} $ 和 $ \ket{y} $，則這項作業會執行下列轉換： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x，y，z) } $。</span><span class="sxs-lookup"><span data-stu-id="6e2a8-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="6e2a8-108">輸入</span><span class="sxs-lookup"><span data-stu-id="6e2a8-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="6e2a8-109">input0： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6e2a8-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6e2a8-110">第一個輸入量子位。</span><span class="sxs-lookup"><span data-stu-id="6e2a8-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="6e2a8-111">input1： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6e2a8-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6e2a8-112">第二個輸入量子位。</span><span class="sxs-lookup"><span data-stu-id="6e2a8-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6e2a8-113">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6e2a8-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6e2a8-114">將套用多數函數的量子位。</span><span class="sxs-lookup"><span data-stu-id="6e2a8-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e2a8-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e2a8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

