---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701167"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


將區塊編碼反映轉換成量子逐步解說。

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>描述

假設有一個 `BlockEncodingReflection` 由單一 $U $ 將某些運算子編碼 $H $，則會將它轉換成量子逐步解說 $W $ 包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的範圍。

## <a name="input"></a>輸入

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding： [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`單一 $U $，以轉換成量子引導。



## <a name="output--qubitqubit--unit-adj--ctl"></a>Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]、[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl

量子逐步解說 $W $ 可共同處理暫存器 `a` ，並 `s` 將 $H $ 的區塊編碼，並包含 $ \pm e ^ {\pm i\sin ^ {-1} (H) } $ 的範圍。

## <a name="references"></a>參考

- Hamiltonian 模擬，量子位化 Guang Hao Low，Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>另請參閱

- [BlockEncoding。](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [BlockEncodingReflection。](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)