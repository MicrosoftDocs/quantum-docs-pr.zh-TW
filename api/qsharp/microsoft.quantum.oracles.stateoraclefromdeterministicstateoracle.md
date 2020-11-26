---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193806"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>StateOracleFromDeterministicStateOracle 函式

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


將型別的 oracle 轉換 `DeterministicStateOracle` 為 `StateOracle` 。

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>輸入

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle： [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

準備 oracle $A $ 類型的狀態 `DeterministicStateOracle` 。



## <a name="output--stateoracle"></a>輸出： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Oracle 的相同狀態準備 $A $，但現在是類型 `StateOracle` 。 請注意，在這種情況下，旗標索引 `StateOracle` 是虛擬變數，沒有任何作用。

## <a name="see-also"></a>另請參閱

- [Oracle. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Oracle. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)