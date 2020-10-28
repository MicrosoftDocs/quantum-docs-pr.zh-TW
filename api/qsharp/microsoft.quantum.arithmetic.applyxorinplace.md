---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 5a35abc16a967e64c84466a47844ed7beeb618dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699958"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="4a2c3-102">ApplyXorInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="4a2c3-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="4a2c3-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4a2c3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4a2c3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a2c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a2c3-105">在傳統整數與量子位暫存器所代表的整數之間套用位 XOR 運算。</span><span class="sxs-lookup"><span data-stu-id="4a2c3-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="4a2c3-106">描述</span><span class="sxs-lookup"><span data-stu-id="4a2c3-106">Description</span></span>

<span data-ttu-id="4a2c3-107">`X`根據整數中的1位，將作業套用至以小到小的暫存器量子位。</span><span class="sxs-lookup"><span data-stu-id="4a2c3-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="4a2c3-108">讓我們 `value` 用來表示，並讓 y 成為以不帶正負號的整數編碼 `target` ，然後 `InPlaceXorLE` 執行下列對應所提供的作業： $ \ket{y}\rightarrow \ket{y\oplus a} $，其中 $ \oplus $ 是位互斥 OR 運算子。</span><span class="sxs-lookup"><span data-stu-id="4a2c3-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="4a2c3-109">輸入</span><span class="sxs-lookup"><span data-stu-id="4a2c3-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="4a2c3-110">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a2c3-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a2c3-111">假設為非負數的整數。</span><span class="sxs-lookup"><span data-stu-id="4a2c3-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="4a2c3-112">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4a2c3-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4a2c3-113">用來儲存以位元組由小到大編碼的量子暫存器 `value` 。</span><span class="sxs-lookup"><span data-stu-id="4a2c3-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a2c3-114">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a2c3-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

