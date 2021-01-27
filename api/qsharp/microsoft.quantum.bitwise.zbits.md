---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842066"
---
# <a name="zbits-function"></a><span data-ttu-id="7e316-102">ZBits 函式</span><span class="sxs-lookup"><span data-stu-id="7e316-102">ZBits function</span></span>

<span data-ttu-id="7e316-103">命名空間： [Microsoft 量子. 位](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="7e316-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="7e316-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7e316-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7e316-105">傳回整數，表示 Pauli 運算子陣列的 Z 位。</span><span class="sxs-lookup"><span data-stu-id="7e316-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="7e316-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7e316-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="7e316-107">paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="7e316-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="7e316-108">Pauli 運算子的陣列，要以整數表示。</span><span class="sxs-lookup"><span data-stu-id="7e316-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="7e316-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7e316-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7e316-110">整數 $x $ 具有二進位表示 $ (p_ {62} \, p_ {61} \, \dots .. \, p_0) $，其中 $p _i = $0，如果 `paulis[i]` 是 `PauliI` 或 `PauliX` ，則為 $p _i = $1 `paulis[i]` `PauliY` `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="7e316-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e316-111">備註</span><span class="sxs-lookup"><span data-stu-id="7e316-111">Remarks</span></span>

<span data-ttu-id="7e316-112">如果陣列的長度大於63，函數將會擲回 `paulis` 。</span><span class="sxs-lookup"><span data-stu-id="7e316-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e316-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7e316-113">See Also</span></span>

- [<span data-ttu-id="7e316-114">XBits。</span><span class="sxs-lookup"><span data-stu-id="7e316-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)