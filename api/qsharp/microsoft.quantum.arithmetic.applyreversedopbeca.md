---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA
title: ApplyReversedOpBECA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBECA
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 1a11b85e4eca627246d7b9d3b4c10824296e9a77
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699983"
---
# <a name="applyreversedopbeca-operation"></a><span data-ttu-id="d5540-102">ApplyReversedOpBECA 操作</span><span class="sxs-lookup"><span data-stu-id="d5540-102">ApplyReversedOpBECA operation</span></span>

<span data-ttu-id="d5540-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d5540-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d5540-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5540-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5540-105">使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="d5540-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBECA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl + Adj), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d5540-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d5540-106">Input</span></span>

### <a name="op--bigendian--unit-ctl--adj"></a><span data-ttu-id="d5540-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="d5540-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d5540-108">在位元組由大到小的暫存器上運作的作業。</span><span class="sxs-lookup"><span data-stu-id="d5540-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="d5540-109">register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d5540-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d5540-110">要轉換的位元組由大到小的暫存器。</span><span class="sxs-lookup"><span data-stu-id="d5540-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5540-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5540-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d5540-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d5540-112">See Also</span></span>

- [<span data-ttu-id="d5540-113">ApplyReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="d5540-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="d5540-114">ApplyReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="d5540-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="d5540-115">ApplyReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="d5540-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)