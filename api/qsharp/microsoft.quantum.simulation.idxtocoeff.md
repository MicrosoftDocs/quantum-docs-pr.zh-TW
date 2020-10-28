---
uid: Microsoft.Quantum.Simulation.IdxToCoeff
title: IdxToCoeff 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToCoeff
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: 50e0c536b01cddb56482580fd634270c4e104173
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700863"
---
# <a name="idxtocoeff-function"></a><span data-ttu-id="94bc3-102">IdxToCoeff 函式</span><span class="sxs-lookup"><span data-stu-id="94bc3-102">IdxToCoeff function</span></span>

<span data-ttu-id="94bc3-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="94bc3-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="94bc3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94bc3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94bc3-105">用於執行 `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="94bc3-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToCoeff (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToCoeff : (Microsoft.Quantum.Simulation.GeneratorIndex -> Double)) : Double
```


## <a name="input"></a><span data-ttu-id="94bc3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="94bc3-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="94bc3-107">idx： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="94bc3-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="94bc3-108">genFun： [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="94bc3-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtocoeff--generatorindex---double"></a><span data-ttu-id="94bc3-109">genIdxToCoeff： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94bc3-109">genIdxToCoeff : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="94bc3-110">輸出： [雙精度浮點數](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="94bc3-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="see-also"></a><span data-ttu-id="94bc3-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="94bc3-111">See Also</span></span>

- [<span data-ttu-id="94bc3-112">PauliBlockEncoding。</span><span class="sxs-lookup"><span data-stu-id="94bc3-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)