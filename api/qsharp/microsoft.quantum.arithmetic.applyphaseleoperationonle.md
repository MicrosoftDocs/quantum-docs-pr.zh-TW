---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: d94fdb55e051e76dd518eff14b80d1a24516bf8a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843669"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="856fc-102">ApplyPhaseLEOperationOnLE 操作</span><span class="sxs-lookup"><span data-stu-id="856fc-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="856fc-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="856fc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="856fc-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="856fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="856fc-105">在類型的目標暫存器 <xref:microsoft.quantum.arithmetic.littleendian> 上套用接受註冊作為輸入的作業 <xref:microsoft.quantum.arithmetic.phaselittleendian> 。</span><span class="sxs-lookup"><span data-stu-id="856fc-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="856fc-106">輸入</span><span class="sxs-lookup"><span data-stu-id="856fc-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="856fc-107">op： [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="856fc-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="856fc-108">要套用的作業。</span><span class="sxs-lookup"><span data-stu-id="856fc-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="856fc-109">目標： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="856fc-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="856fc-110">要套用作業的註冊。</span><span class="sxs-lookup"><span data-stu-id="856fc-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="856fc-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="856fc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="856fc-112">備註</span><span class="sxs-lookup"><span data-stu-id="856fc-112">Remarks</span></span>

<span data-ttu-id="856fc-113">註冊會透過使用來轉換成 `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ，然後在應用程式之後，再傳回其原始標記法 `op` 。</span><span class="sxs-lookup"><span data-stu-id="856fc-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="856fc-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="856fc-114">See Also</span></span>

- [<span data-ttu-id="856fc-115">Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="856fc-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="856fc-116">Canon. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="856fc-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="856fc-117">Canon. ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="856fc-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)