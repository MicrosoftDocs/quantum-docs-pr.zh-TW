---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699898"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="7740e-102">CopyMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="7740e-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="7740e-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7740e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7740e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7740e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7740e-105">將代表不帶正負號整數的量子位暫存器最重要的位複製 `from` 到量子位中 `target` 。</span><span class="sxs-lookup"><span data-stu-id="7740e-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="7740e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7740e-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="7740e-107">來源： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7740e-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7740e-108">從中複製最大位的不帶正負號整數。</span><span class="sxs-lookup"><span data-stu-id="7740e-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="7740e-109">以位元組由小到大格式編碼的整數。</span><span class="sxs-lookup"><span data-stu-id="7740e-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7740e-110">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7740e-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7740e-111">要在其中複製最大位的量子位。</span><span class="sxs-lookup"><span data-stu-id="7740e-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="7740e-112">位編碼是以計算為基礎。</span><span class="sxs-lookup"><span data-stu-id="7740e-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7740e-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7740e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7740e-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7740e-114">See Also</span></span>

- [<span data-ttu-id="7740e-115">LittleEndian。</span><span class="sxs-lookup"><span data-stu-id="7740e-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)