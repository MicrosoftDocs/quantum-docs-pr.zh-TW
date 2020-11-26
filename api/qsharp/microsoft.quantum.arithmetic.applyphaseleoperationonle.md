---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: adccad53e8d874cb2879d7005711624bbcc69201
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190763"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="62ce2-102">ApplyPhaseLEOperationOnLE 操作</span><span class="sxs-lookup"><span data-stu-id="62ce2-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="62ce2-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="62ce2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="62ce2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62ce2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62ce2-105">在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.littleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.phaselittleendian> 。</span><span class="sxs-lookup"><span data-stu-id="62ce2-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="62ce2-106">輸入</span><span class="sxs-lookup"><span data-stu-id="62ce2-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="62ce2-107">op： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62ce2-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="62ce2-108">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="62ce2-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="62ce2-109">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="62ce2-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="62ce2-110">要套用作業的註冊。</span><span class="sxs-lookup"><span data-stu-id="62ce2-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62ce2-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62ce2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="62ce2-112">備註</span><span class="sxs-lookup"><span data-stu-id="62ce2-112">Remarks</span></span>

<span data-ttu-id="62ce2-113">註冊會透過使用來轉換成 `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。</span><span class="sxs-lookup"><span data-stu-id="62ce2-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="62ce2-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="62ce2-114">See Also</span></span>

- [<span data-ttu-id="62ce2-115">Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="62ce2-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="62ce2-116">Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="62ce2-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="62ce2-117">Canon. ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="62ce2-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)