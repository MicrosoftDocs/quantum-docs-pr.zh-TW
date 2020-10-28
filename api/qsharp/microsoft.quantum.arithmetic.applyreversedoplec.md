---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: ApplyReversedOpLEC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: ac9a6000140445a457a9abc46d5143dcb089883e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699975"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="17d15-102">ApplyReversedOpLEC 操作</span><span class="sxs-lookup"><span data-stu-id="17d15-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="17d15-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="17d15-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="17d15-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17d15-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17d15-105">使用位元組由大到小的格式，將採用位元組由小到大輸入的作業套用至暫存器編碼的不帶正負號的整數。</span><span class="sxs-lookup"><span data-stu-id="17d15-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="17d15-106">輸入</span><span class="sxs-lookup"><span data-stu-id="17d15-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="17d15-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="17d15-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="17d15-108">以位元組由小到大的暫存器為運算的作業。</span><span class="sxs-lookup"><span data-stu-id="17d15-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="17d15-109">register： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="17d15-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="17d15-110">要轉換的位元組由大到小的暫存器。</span><span class="sxs-lookup"><span data-stu-id="17d15-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17d15-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17d15-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="17d15-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="17d15-112">See Also</span></span>

- [<span data-ttu-id="17d15-113">ApplyReversedOpLE。</span><span class="sxs-lookup"><span data-stu-id="17d15-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="17d15-114">ApplyReversedOpLEA。</span><span class="sxs-lookup"><span data-stu-id="17d15-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="17d15-115">ApplyReversedOpLECA。</span><span class="sxs-lookup"><span data-stu-id="17d15-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)