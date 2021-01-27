---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853205"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="04514-102">_ExtractLogicalQubitFromSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="04514-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="04514-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="04514-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="04514-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04514-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04514-105">症狀測量和內嵌的反向。</span><span class="sxs-lookup"><span data-stu-id="04514-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="04514-106">$X $-和 $Z $-stabilizers 不會平均處理，這是因為編碼電路的特殊選擇。</span><span class="sxs-lookup"><span data-stu-id="04514-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="04514-107">這種不對稱會導致不同的症狀解壓縮常式。</span><span class="sxs-lookup"><span data-stu-id="04514-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="04514-108">您可以直接在程式碼狀態上測量多量子位 Pauli 運算子來測量症狀，但是針對公司用途，邏輯量子位會傳回單一量子位，但在此情況下，不需要進一步 ancillas 即可完成這些症狀測量。</span><span class="sxs-lookup"><span data-stu-id="04514-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="04514-109">輸入</span><span class="sxs-lookup"><span data-stu-id="04514-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="04514-110">程式碼： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="04514-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="04514-111">Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[int](xref:microsoft.quantum.lang-ref.int)、[int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="04514-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="04514-112">邏輯量子位以及一對 $X $-症狀和 $Z $-症狀的整數。</span><span class="sxs-lookup"><span data-stu-id="04514-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="04514-113">它們代表程式碼量子位的索引，其中單一 $X $ 或 $Z $-錯誤會造成測量的症狀。</span><span class="sxs-lookup"><span data-stu-id="04514-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="04514-114">備註</span><span class="sxs-lookup"><span data-stu-id="04514-114">Remarks</span></span>

<span data-ttu-id="04514-115">請注意，這項作業不會標示為 `internal` ，因為單元測試會直接相依于這項作業。</span><span class="sxs-lookup"><span data-stu-id="04514-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="04514-116">基於未來的改進，單元測試應該重構，才能直接相依于公用 callables。</span><span class="sxs-lookup"><span data-stu-id="04514-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="04514-117">此常式是針對 Steane 的7量子位程式碼的特定編碼電路量身打造;如果已修改編碼電路，則可能必須以不同的方式解釋症狀結果。</span><span class="sxs-lookup"><span data-stu-id="04514-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>