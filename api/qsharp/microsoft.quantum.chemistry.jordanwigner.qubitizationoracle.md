---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: QubitizationOracle 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: d67cf10b7516c638df6f5d13cd548bf6696443fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214444"
---
# <a name="qubitizationoracle-function"></a>QubitizationOracle 函式

命名空間： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

封裝： [Microsoft 量子化學](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


傳回量子位化作業和執行所需的參數。

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>輸入

### <a name="qsharpdata--jordanwignerencodingdata"></a>qSharpData： [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian 以 `JordanWignerEncodingData` 格式描述。



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Output： ([Int](xref:microsoft.quantum.lang-ref.int)， ([Double](xref:microsoft.quantum.lang-ref.double)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl) # A3

元組，其中：是配置的 `Int` 量子位數目、 `Double` 是 Hamiltonian 係數的一種，而且作業是量子位化所建立的量子行程。