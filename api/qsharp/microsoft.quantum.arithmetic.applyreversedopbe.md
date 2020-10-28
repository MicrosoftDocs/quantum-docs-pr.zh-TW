---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBE
title: ApplyReversedOpBE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBE
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: a181cb16d6ae7684d49fe200d72bcbf5209018e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699998"
---
# <a name="applyreversedopbe-operation"></a><span data-ttu-id="8b290-102">ApplyReversedOpBE 操作</span><span class="sxs-lookup"><span data-stu-id="8b290-102">ApplyReversedOpBE operation</span></span>

<span data-ttu-id="8b290-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8b290-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8b290-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b290-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b290-105">使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="8b290-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="8b290-106">輸入</span><span class="sxs-lookup"><span data-stu-id="8b290-106">Input</span></span>

### <a name="op--bigendian--unit"></a><span data-ttu-id="8b290-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b290-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8b290-108">在位元組由大到小的暫存器上運作的作業。</span><span class="sxs-lookup"><span data-stu-id="8b290-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="8b290-109">register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8b290-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8b290-110">要轉換的位元組由大到小的暫存器。</span><span class="sxs-lookup"><span data-stu-id="8b290-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b290-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b290-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8b290-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8b290-112">See Also</span></span>

- [<span data-ttu-id="8b290-113">ApplyReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="8b290-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="8b290-114">ApplyReversedOpBEC。</span><span class="sxs-lookup"><span data-stu-id="8b290-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [<span data-ttu-id="8b290-115">ApplyReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="8b290-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)