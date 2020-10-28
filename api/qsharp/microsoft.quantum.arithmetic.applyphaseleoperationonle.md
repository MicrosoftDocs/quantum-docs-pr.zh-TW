---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: dacc52766cf72d2bd562b76fc4939f962133e9a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700010"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="f44b5-102">ApplyPhaseLEOperationOnLE 操作</span><span class="sxs-lookup"><span data-stu-id="f44b5-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="f44b5-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f44b5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f44b5-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f44b5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f44b5-105">在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.littleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.phaselittleendian> 。</span><span class="sxs-lookup"><span data-stu-id="f44b5-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="f44b5-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f44b5-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="f44b5-107">op： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f44b5-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f44b5-108">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="f44b5-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="f44b5-109">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f44b5-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f44b5-110">要套用作業的註冊。</span><span class="sxs-lookup"><span data-stu-id="f44b5-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f44b5-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f44b5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f44b5-112">備註</span><span class="sxs-lookup"><span data-stu-id="f44b5-112">Remarks</span></span>

<span data-ttu-id="f44b5-113">註冊會透過使用來轉換成 `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。</span><span class="sxs-lookup"><span data-stu-id="f44b5-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f44b5-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f44b5-114">See Also</span></span>

- [<span data-ttu-id="f44b5-115">Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="f44b5-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="f44b5-116">Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="f44b5-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="f44b5-117">Canon. ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="f44b5-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)