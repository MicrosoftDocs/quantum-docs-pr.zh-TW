---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851046"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將區塊編碼反映轉換成量子逐步解說。

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>描述

假設有一個 `BlockEncodingReflection` 由單一 $U $ 將某些運算子編碼 $H $，則會將它轉換成量子逐步解說 $W $ 包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的範圍。

## <a name="input"></a>輸入

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`單一 $U $，以轉換成量子引導。



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit)  是形容詞 + Ctl

量子逐步解說 $W $ 可共同處理暫存器 `a` ，並 `s` 將 $H $ 的區塊編碼，並包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的範圍。

## <a name="references"></a>參考資料

- Hamiltonian 模擬，量子位化 Guang Hao Low，Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>另請參閱

- [BlockEncoding。](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)