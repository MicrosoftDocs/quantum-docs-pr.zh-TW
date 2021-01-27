---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853589"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="915f0-102">_assertEqualOnBasisVector 操作</span><span class="sxs-lookup"><span data-stu-id="915f0-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="915f0-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="915f0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="915f0-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="915f0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="915f0-105">檢查套用兩項作業的結果 `givenU` 和 `expectedU` 基礎狀態是否相同。</span><span class="sxs-lookup"><span data-stu-id="915f0-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="915f0-106">基礎狀態是由參數所描述 `basis` 。</span><span class="sxs-lookup"><span data-stu-id="915f0-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="915f0-107"><xref:microsoft.quantum.extensions.fliptobasis>如需此描述的詳細資訊，請參閱函式。</span><span class="sxs-lookup"><span data-stu-id="915f0-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="915f0-108">輸入</span><span class="sxs-lookup"><span data-stu-id="915f0-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="915f0-109">基礎： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="915f0-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="915f0-110">針對每個 $n $ 量子位，以單一量子位基礎狀態識別碼指定的基礎狀態 (0 <= 識別碼 <= 3) 。</span><span class="sxs-lookup"><span data-stu-id="915f0-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="915f0-111">givenU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="915f0-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="915f0-112">要檢查 $n $ 量子位上的作業。</span><span class="sxs-lookup"><span data-stu-id="915f0-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="915f0-113">expectedU： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞</span><span class="sxs-lookup"><span data-stu-id="915f0-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="915f0-114">要與 givenU 比較的 $n $ 量子位上的參考作業。</span><span class="sxs-lookup"><span data-stu-id="915f0-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="915f0-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="915f0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

