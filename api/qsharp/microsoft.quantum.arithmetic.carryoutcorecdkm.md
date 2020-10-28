---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699927"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="8b3d4-102">CarryOutCoreCDKM 操作</span><span class="sxs-lookup"><span data-stu-id="8b3d4-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="8b3d4-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8b3d4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8b3d4-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b3d4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b3d4-105">RippleCarryAdderCDKM 中的核心作業，用於上述 ApplyOuterCDKMAdder 作業，也就是 conjugated 與此作業，以取得 RippleCarryAdderCDKM 的內部作業。</span><span class="sxs-lookup"><span data-stu-id="8b3d4-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="8b3d4-106">這項作業會計算執行量子位，並在輸入的部分套用非閘道序列 `ys` 。</span><span class="sxs-lookup"><span data-stu-id="8b3d4-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8b3d4-107">輸入</span><span class="sxs-lookup"><span data-stu-id="8b3d4-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="8b3d4-108">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8b3d4-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8b3d4-109">第一個量子位報名。</span><span class="sxs-lookup"><span data-stu-id="8b3d4-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="8b3d4-110">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8b3d4-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8b3d4-111">第二個量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="8b3d4-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="8b3d4-112">ancilla： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8b3d4-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8b3d4-113">在 RippleCarryAdderCDKM 中使用的 ancilla 量子位會傳遞至這項作業。</span><span class="sxs-lookup"><span data-stu-id="8b3d4-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="8b3d4-114">攜帶： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8b3d4-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8b3d4-115">在 RippleCarryAdderCDKM 作業中執行量子位。</span><span class="sxs-lookup"><span data-stu-id="8b3d4-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b3d4-116">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b3d4-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="8b3d4-117">參考</span><span class="sxs-lookup"><span data-stu-id="8b3d4-117">References</span></span>

- <span data-ttu-id="8b3d4-118">Steven Cuccaro、Thomas g. Draper、Samuel A. Kutin、David Petrie Moulton：「新的量子 ripple-攜帶加法電路」、2004。</span><span class="sxs-lookup"><span data-stu-id="8b3d4-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1