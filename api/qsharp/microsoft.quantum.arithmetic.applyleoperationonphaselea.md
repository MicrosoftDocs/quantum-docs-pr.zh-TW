---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEA
title: ApplyLEOperationOnPhaseLEA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 572c66b201b6d2c816017230527c70c1b3c83371
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700035"
---
# <a name="applyleoperationonphaselea-operation"></a><span data-ttu-id="c5dcf-102">ApplyLEOperationOnPhaseLEA 操作</span><span class="sxs-lookup"><span data-stu-id="c5dcf-102">ApplyLEOperationOnPhaseLEA operation</span></span>

<span data-ttu-id="c5dcf-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c5dcf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c5dcf-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5dcf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5dcf-105">在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.phaselittleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.littleendian> 。</span><span class="sxs-lookup"><span data-stu-id="c5dcf-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="c5dcf-106">輸入</span><span class="sxs-lookup"><span data-stu-id="c5dcf-106">Input</span></span>

### <a name="op--littleendian--unit-adj"></a><span data-ttu-id="c5dcf-107">op： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞</span><span class="sxs-lookup"><span data-stu-id="c5dcf-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c5dcf-108">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="c5dcf-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="c5dcf-109">目標： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5dcf-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="c5dcf-110">要套用作業的註冊。</span><span class="sxs-lookup"><span data-stu-id="c5dcf-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5dcf-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5dcf-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c5dcf-112">備註</span><span class="sxs-lookup"><span data-stu-id="c5dcf-112">Remarks</span></span>

<span data-ttu-id="c5dcf-113">註冊會透過使用來轉換成 `LittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c5dcf-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5dcf-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c5dcf-114">See Also</span></span>

- [<span data-ttu-id="c5dcf-115">Canon. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="c5dcf-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="c5dcf-116">Canon. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="c5dcf-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="c5dcf-117">Canon. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="c5dcf-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)