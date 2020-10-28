---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC
title: ApplyReversedOpBEC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpBEC
qsharp.summary: Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.
ms.openlocfilehash: 54c35ccea5e9c2d3ec7a3e6f325f78c3e602970e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699986"
---
# <a name="applyreversedopbec-operation"></a><span data-ttu-id="40637-102">ApplyReversedOpBEC 操作</span><span class="sxs-lookup"><span data-stu-id="40637-102">ApplyReversedOpBEC operation</span></span>

<span data-ttu-id="40637-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="40637-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="40637-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="40637-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="40637-105">使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="40637-105">Applies an operation that takes big-endian input to a register encoding an unsigned integer using little-endian format.</span></span>

```qsharp
operation ApplyReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="40637-106">輸入</span><span class="sxs-lookup"><span data-stu-id="40637-106">Input</span></span>

### <a name="op--bigendian--unit-ctl"></a><span data-ttu-id="40637-107">op： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="40637-107">op : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="40637-108">在位元組由大到小的暫存器上運作的作業。</span><span class="sxs-lookup"><span data-stu-id="40637-108">Operation that acts on a big-endian register.</span></span>


### <a name="register--littleendian"></a><span data-ttu-id="40637-109">register： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="40637-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="40637-110">要轉換的位元組由大到小的暫存器。</span><span class="sxs-lookup"><span data-stu-id="40637-110">A little-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40637-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40637-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="40637-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="40637-112">See Also</span></span>

- [<span data-ttu-id="40637-113">ApplyReversedOpBE。</span><span class="sxs-lookup"><span data-stu-id="40637-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpBE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [<span data-ttu-id="40637-114">ApplyReversedOpBEA。</span><span class="sxs-lookup"><span data-stu-id="40637-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [<span data-ttu-id="40637-115">ApplyReversedOpBECA。</span><span class="sxs-lookup"><span data-stu-id="40637-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBECA)