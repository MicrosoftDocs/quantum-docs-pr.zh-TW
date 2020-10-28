---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEC
title: ApplyLEOperationOnPhaseLEC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEC
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 6accddf4f46c0939c418e164ccb153a8fc6e358d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700034"
---
# <a name="applyleoperationonphaselec-operation"></a><span data-ttu-id="5af1e-102">ApplyLEOperationOnPhaseLEC 操作</span><span class="sxs-lookup"><span data-stu-id="5af1e-102">ApplyLEOperationOnPhaseLEC operation</span></span>

<span data-ttu-id="5af1e-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5af1e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5af1e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5af1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5af1e-105">在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.phaselittleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.littleendian> 。</span><span class="sxs-lookup"><span data-stu-id="5af1e-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="5af1e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="5af1e-106">Input</span></span>

### <a name="op--littleendian--unit-ctl"></a><span data-ttu-id="5af1e-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="5af1e-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5af1e-108">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="5af1e-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="5af1e-109">目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5af1e-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="5af1e-110">要套用作業的註冊。</span><span class="sxs-lookup"><span data-stu-id="5af1e-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5af1e-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5af1e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5af1e-112">備註</span><span class="sxs-lookup"><span data-stu-id="5af1e-112">Remarks</span></span>

<span data-ttu-id="5af1e-113">註冊會透過使用來轉換成 `LittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。</span><span class="sxs-lookup"><span data-stu-id="5af1e-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5af1e-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5af1e-114">See Also</span></span>

- [<span data-ttu-id="5af1e-115">Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="5af1e-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="5af1e-116">Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="5af1e-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="5af1e-117">Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="5af1e-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)