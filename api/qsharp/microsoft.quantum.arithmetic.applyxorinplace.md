---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210104"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="dd74b-102">ApplyXorInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="dd74b-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="dd74b-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dd74b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dd74b-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd74b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd74b-105">在傳統整數與量子位暫存器所代表的整數之間套用位 XOR 運算。</span><span class="sxs-lookup"><span data-stu-id="dd74b-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="dd74b-106">描述</span><span class="sxs-lookup"><span data-stu-id="dd74b-106">Description</span></span>

<span data-ttu-id="dd74b-107">`X`根據整數中的1位，將作業套用至以小到小的暫存器量子位。</span><span class="sxs-lookup"><span data-stu-id="dd74b-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="dd74b-108">讓我們 `value` 用來表示，並讓 y 成為以不帶正負號的整數編碼 `target` ，然後 `InPlaceXorLE` 執行下列對應所提供的作業： $ \ket{y}\rightarrow \ket{y\oplus a} $，其中 $ \oplus $ 是位互斥 OR 運算子。</span><span class="sxs-lookup"><span data-stu-id="dd74b-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="dd74b-109">輸入</span><span class="sxs-lookup"><span data-stu-id="dd74b-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="dd74b-110">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd74b-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd74b-111">假設為非負數的整數。</span><span class="sxs-lookup"><span data-stu-id="dd74b-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="dd74b-112">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dd74b-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dd74b-113">用來儲存以位元組由小到大編碼的量子暫存器 `value` 。</span><span class="sxs-lookup"><span data-stu-id="dd74b-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dd74b-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dd74b-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

