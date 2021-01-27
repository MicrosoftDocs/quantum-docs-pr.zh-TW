---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: FlipMasks 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859130"
---
# <a name="flipmasks-function"></a>FlipMasks 函式

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對每個2層級的單一計算「翻轉遮罩」，這代表應該在套用對應的1量子位閘道之前和之後反轉的量子位。
為了方便起見，在前面加上0的結果。

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a>輸入

### <a name="decomposition--complexintint"></a>分解： ([Complex](xref:Microsoft.Quantum.Math.Complex)[] []、[int](xref:microsoft.quantum.lang-ref.int)、[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="allqubitsmask--int"></a>allQubitsMask： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

