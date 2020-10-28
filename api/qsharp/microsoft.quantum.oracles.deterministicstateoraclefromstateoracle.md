---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700790"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle 函式

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

包： [](https://nuget.org/packages/)


將型別的 oracle 轉換 `StateOracle` 為 `DeterministicStateOracle` 。

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>輸入

### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

$A $ 之旗標量子位的索引 `stateOracle` ，它會明確地在兩個暫存器上執行：旗標 $f $ 和 system $s $，例如 $A \ket {0} \_ f\ket {\ psi} \_ s $。


### <a name="stateoracle--stateoracle"></a>stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

準備 oracle $A $ 類型的狀態 `StateOracle` 。



## <a name="output--deterministicstateoracle"></a>輸出： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Oracle 的相同狀態準備 $A $，但現在的型別是 `DeterministicStateOracle` ，因此它是在 $a 不會再明確分隔的登錄上，例如 $A \ket{0\psi} \_ {as} $。

## <a name="see-also"></a>另請參閱

- [Oracle. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Oracle. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)