---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLE
title: ApplyLEOperationOnPhaseLE 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 33e6cb81916737bf5db467e10fd2aeebb619116a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190899"
---
# <a name="applyleoperationonphasele-operation"></a><span data-ttu-id="c7108-102">ApplyLEOperationOnPhaseLE 操作</span><span class="sxs-lookup"><span data-stu-id="c7108-102">ApplyLEOperationOnPhaseLE operation</span></span>

<span data-ttu-id="c7108-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c7108-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c7108-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c7108-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c7108-105">在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.phaselittleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.littleendian> 。</span><span class="sxs-lookup"><span data-stu-id="c7108-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c7108-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c7108-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="c7108-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7108-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c7108-108">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="c7108-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="c7108-109">目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7108-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="c7108-110">要套用作業的註冊。</span><span class="sxs-lookup"><span data-stu-id="c7108-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7108-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7108-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c7108-112">備註</span><span class="sxs-lookup"><span data-stu-id="c7108-112">Remarks</span></span>

<span data-ttu-id="c7108-113">註冊會透過使用來轉換成 `LittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c7108-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7108-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c7108-114">See Also</span></span>

- [<span data-ttu-id="c7108-115">Canon. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="c7108-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="c7108-116">Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="c7108-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="c7108-117">Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="c7108-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)