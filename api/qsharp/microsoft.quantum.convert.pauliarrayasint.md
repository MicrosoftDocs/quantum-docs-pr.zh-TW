---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832715"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="9874c-102">PauliArrayAsInt 函式</span><span class="sxs-lookup"><span data-stu-id="9874c-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="9874c-103">命名空間： [Microsoft 量子. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="9874c-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="9874c-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9874c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9874c-105">將以單一量子位 Pauli 運算子陣列表示的多量子位 Pauli 運算子編碼為整數。</span><span class="sxs-lookup"><span data-stu-id="9874c-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="9874c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9874c-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="9874c-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9874c-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="9874c-108">最多31個單一量子位 Pauli 運算子的陣列。</span><span class="sxs-lookup"><span data-stu-id="9874c-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="9874c-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9874c-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9874c-110">唯一識別的整數 `paulis` ，如下所述。</span><span class="sxs-lookup"><span data-stu-id="9874c-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="9874c-111">備註</span><span class="sxs-lookup"><span data-stu-id="9874c-111">Remarks</span></span>

<span data-ttu-id="9874c-112">每個 Pauli 運算子都可以使用兩個位進行編碼： $ $ \begin{align} \boldone \mapsto 00、\quad X \mapsto 01、\quad Y \mapsto 11、\quad Z \mapsto 10。</span><span class="sxs-lookup"><span data-stu-id="9874c-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="9874c-113">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9874c-113">\end{align} $$</span></span>

<span data-ttu-id="9874c-114">根據 Pauli 運算子的陣列 `[P0, ..., Pn]` ，此函式會以位元組由大到小的順序串連每個 Pauli 運算子的對應，以傳回以二進位擴充形成的整數 `bits(Pn) ... bits(P0)` 。</span><span class="sxs-lookup"><span data-stu-id="9874c-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>