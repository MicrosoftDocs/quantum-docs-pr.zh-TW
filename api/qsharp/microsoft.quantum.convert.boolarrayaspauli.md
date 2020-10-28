---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c5ef71322dae248fc2c6b1db3adf891de7d72488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698331"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="0c120-102">BoolArrayAsPauli 函式</span><span class="sxs-lookup"><span data-stu-id="0c120-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="0c120-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="0c120-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="0c120-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c120-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c120-105">指定一個位字串，會傳回多量子位的 Pauli 運算子，以單一量子位 Pauli 運算子的陣列表示。</span><span class="sxs-lookup"><span data-stu-id="0c120-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="0c120-106">輸入</span><span class="sxs-lookup"><span data-stu-id="0c120-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="0c120-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="0c120-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="0c120-108">Pauli 運算子，適用于量子位 where `bitsApply == bits[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="0c120-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="0c120-109">bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0c120-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0c120-110">如果位為此值，則套用 Pauli。</span><span class="sxs-lookup"><span data-stu-id="0c120-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="0c120-111">位： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0c120-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="0c120-112">布林陣列。</span><span class="sxs-lookup"><span data-stu-id="0c120-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="0c120-113">輸出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="0c120-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="0c120-114">備註</span><span class="sxs-lookup"><span data-stu-id="0c120-114">Remarks</span></span>

<span data-ttu-id="0c120-115">布林陣列和量子暫存器的長度必須相等。</span><span class="sxs-lookup"><span data-stu-id="0c120-115">The Boolean array and the quantum register must be of equal length.</span></span>