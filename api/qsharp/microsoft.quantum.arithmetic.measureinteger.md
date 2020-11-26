---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222638"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="c084c-102">MeasureInteger 操作</span><span class="sxs-lookup"><span data-stu-id="c084c-102">MeasureInteger operation</span></span>

<span data-ttu-id="c084c-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c084c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c084c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c084c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c084c-105">測量量子暫存器的內容，並將它轉換成整數。</span><span class="sxs-lookup"><span data-stu-id="c084c-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="c084c-106">測量是以標準計算為基礎來執行，亦即，的 eigenbasis `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="c084c-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="c084c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="c084c-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="c084c-108">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c084c-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c084c-109">以位元組由大到小的編碼方式的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="c084c-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="c084c-110">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c084c-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c084c-111">不帶正負號的整數，其中包含的測量值 `target` 。</span><span class="sxs-lookup"><span data-stu-id="c084c-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c084c-112">備註</span><span class="sxs-lookup"><span data-stu-id="c084c-112">Remarks</span></span>

<span data-ttu-id="c084c-113">此作業會將其輸入暫存器重設為 $ \ket{00\cdots 0} $ 狀態，適合用來釋回目的電腦。</span><span class="sxs-lookup"><span data-stu-id="c084c-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="c084c-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c084c-114">See Also</span></span>

- [<span data-ttu-id="c084c-115">Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="c084c-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)