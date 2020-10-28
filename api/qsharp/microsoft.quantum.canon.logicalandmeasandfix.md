---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698985"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="b7f28-102">LogicalANDMeasAndFix 操作</span><span class="sxs-lookup"><span data-stu-id="b7f28-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="b7f28-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b7f28-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b7f28-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7f28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7f28-105">計算多個量子位的邏輯 AND。</span><span class="sxs-lookup"><span data-stu-id="b7f28-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b7f28-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b7f28-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="b7f28-107">ctrlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b7f28-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b7f28-108">量子位輸入至多個輸入和閘道。</span><span class="sxs-lookup"><span data-stu-id="b7f28-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b7f28-109">目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b7f28-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b7f28-110">量子位，以及寫入的輸出。</span><span class="sxs-lookup"><span data-stu-id="b7f28-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="b7f28-111">這會假設一律以 $ \ket {0} $ 狀態開始。</span><span class="sxs-lookup"><span data-stu-id="b7f28-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7f28-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7f28-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b7f28-113">備註</span><span class="sxs-lookup"><span data-stu-id="b7f28-113">Remarks</span></span>

<span data-ttu-id="b7f28-114">當 `ctrlRegister` 只有 $2 $ 量子位時，這相當於作業， `CCNOT` 但階段 $e ^ {i \ Pi/2} $ on $ \ket {001} $ 和 $-e ^ {i \ pi/2} $ on $ \ket {101} $ 和 $ \ket {011} $。</span><span class="sxs-lookup"><span data-stu-id="b7f28-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="b7f28-115">Adjoint 也是測量和修復方法，它只是在特殊情況下的原始作業反向 (請參閱) 的參考，但使用較少的 T 閘道。</span><span class="sxs-lookup"><span data-stu-id="b7f28-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="b7f28-116">參考</span><span class="sxs-lookup"><span data-stu-id="b7f28-116">References</span></span>

- [<span data-ttu-id="b7f28-117">*Craig Gidney* ，1709.06648</span><span class="sxs-lookup"><span data-stu-id="b7f28-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)