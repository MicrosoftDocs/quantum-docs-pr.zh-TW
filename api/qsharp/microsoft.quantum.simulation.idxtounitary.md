---
uid: Microsoft.Quantum.Simulation.IdxToUnitary
title: IdxToUnitary 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToUnitary
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: dd13b2d2e846dcddb820599ea26aa25b90903dbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229268"
---
# <a name="idxtounitary-function"></a><span data-ttu-id="04bf7-102">IdxToUnitary 函式</span><span class="sxs-lookup"><span data-stu-id="04bf7-102">IdxToUnitary function</span></span>

<span data-ttu-id="04bf7-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="04bf7-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="04bf7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04bf7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04bf7-105">用於執行 `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="04bf7-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToUnitary (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToUnitary : (Microsoft.Quantum.Simulation.GeneratorIndex -> (Qubit[] => Unit is Adj + Ctl))) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="04bf7-106">輸入</span><span class="sxs-lookup"><span data-stu-id="04bf7-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="04bf7-107">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04bf7-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="04bf7-108">genFun： [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="04bf7-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtounitary--generatorindex---qubit--unit--is-adj--ctl"></a><span data-ttu-id="04bf7-109">genIdxToUnitary： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="04bf7-109">genIdxToUnitary : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="04bf7-110">輸出： [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="04bf7-110">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="04bf7-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="04bf7-111">See Also</span></span>

- [<span data-ttu-id="04bf7-112">PauliBlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="04bf7-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)