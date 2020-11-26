---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203258"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a><span data-ttu-id="3eb92-102">ApplyXControlledOnTruthTableWithCleanTarget 操作</span><span class="sxs-lookup"><span data-stu-id="3eb92-102">ApplyXControlledOnTruthTableWithCleanTarget operation</span></span>

<span data-ttu-id="3eb92-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3eb92-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3eb92-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3eb92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3eb92-105">@"microsoft.quantum.intrinsic.x" `target` 如果布耳函數 `func` 針對中的傳統指派評估為 true，則會在上套用運算 `controlRegister` 。</span><span class="sxs-lookup"><span data-stu-id="3eb92-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3eb92-106">描述</span><span class="sxs-lookup"><span data-stu-id="3eb92-106">Description</span></span>

<span data-ttu-id="3eb92-107">這項作業會執行特殊案例 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" ，在此案例中，目標量子位已知為 $ \ket {0} $ 狀態。</span><span class="sxs-lookup"><span data-stu-id="3eb92-107">This operation implements a special case of @"microsoft.quantum.synthesis.applyxcontrolledontruthtable", in which the target qubit is known to be in the $\ket{0}$ state.</span></span>

<span data-ttu-id="3eb92-108">執行會使用和網 @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" 關。</span><span class="sxs-lookup"><span data-stu-id="3eb92-108">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>  <span data-ttu-id="3eb92-109">Adjoint 作業的實作為優化，並使用以度量為基礎的 uncomputation。</span><span class="sxs-lookup"><span data-stu-id="3eb92-109">The implementation of the adjoint operation is optimized and uses measurement-based uncomputation.</span></span>

## <a name="input"></a><span data-ttu-id="3eb92-110">輸入</span><span class="sxs-lookup"><span data-stu-id="3eb92-110">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="3eb92-111">func： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3eb92-111">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3eb92-112">以大整數表示的布林事實資料表</span><span class="sxs-lookup"><span data-stu-id="3eb92-112">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="3eb92-113">controlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3eb92-113">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3eb92-114">註冊控制項量子位</span><span class="sxs-lookup"><span data-stu-id="3eb92-114">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3eb92-115">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3eb92-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3eb92-116">目標量子位 (必須是 $ \ket {0} $ state) </span><span class="sxs-lookup"><span data-stu-id="3eb92-116">Target qubit (must be in $\ket{0}$ state)</span></span>



## <a name="output--unit"></a><span data-ttu-id="3eb92-117">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3eb92-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3eb92-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3eb92-118">See Also</span></span>

- [<span data-ttu-id="3eb92-119">ApplyXControlledOnTruthTable。</span><span class="sxs-lookup"><span data-stu-id="3eb92-119">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)