---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: MultiplexerBruteForceFromGenerator 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad388bd34a778a7d774cd2a5118399b3db45267d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698981"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a>MultiplexerBruteForceFromGenerator 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


傳回 $U $ 的乘法控制項單一作業，此作業會在由 n-量子位 number state $ \ket{j} $ 控制時套用單一 $V _j $。

$U = \sum ^ {2 ^ n-1-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="unitarygenerator--intint---qubit--unit-adj--ctl"></a>unitaryGenerator： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int) -> [量子位](xref:microsoft.quantum.lang-ref.qubit)[] => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl) 

元組，其中第一個專案 `Int` 是 unitaries $N $ 的數目，而第二個元素 `(Int -> ('T => () is Adj + Ctl))` 是採用整數 $j $ in $ [0，n-1] $ 的函式，並輸出單一作業 $V _j $。



## <a name="output--littleendianqubit--unit-adj--ctl"></a>Output： ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

$U $ 的乘法受控制的單一作業，套用所描述的 unitaries `unitaryGenerator` 。

## <a name="see-also"></a>另請參閱

- [Canon. MultiplexerBruteForceFromGenerator](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)