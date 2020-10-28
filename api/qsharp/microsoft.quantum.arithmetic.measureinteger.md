---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699815"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="432a9-102">MeasureInteger 操作</span><span class="sxs-lookup"><span data-stu-id="432a9-102">MeasureInteger operation</span></span>

<span data-ttu-id="432a9-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="432a9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="432a9-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="432a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="432a9-105">測量量子暫存器的內容，並將它轉換成整數。</span><span class="sxs-lookup"><span data-stu-id="432a9-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="432a9-106">測量是以標準計算為基礎來執行，亦即，的 eigenbasis `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="432a9-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="432a9-107">輸入</span><span class="sxs-lookup"><span data-stu-id="432a9-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="432a9-108">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="432a9-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="432a9-109">以位元組由大到小的編碼方式的量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="432a9-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="432a9-110">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="432a9-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="432a9-111">不帶正負號的整數，其中包含的測量值 `target` 。</span><span class="sxs-lookup"><span data-stu-id="432a9-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="432a9-112">備註</span><span class="sxs-lookup"><span data-stu-id="432a9-112">Remarks</span></span>

<span data-ttu-id="432a9-113">此作業會將其輸入暫存器重設為 $ \ket{00\cdots 0} $ 狀態，適合用來釋回目的電腦。</span><span class="sxs-lookup"><span data-stu-id="432a9-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="432a9-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="432a9-114">See Also</span></span>

- [<span data-ttu-id="432a9-115">Canon. MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="432a9-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)