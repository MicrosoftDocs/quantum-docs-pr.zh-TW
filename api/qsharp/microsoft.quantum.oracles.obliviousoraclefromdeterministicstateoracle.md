---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700210"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a>ObliviousOracleFromDeterministicStateOracle 函式

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

包： [](https://nuget.org/packages/)


結合了 oracle `DeterministicStateOracle` 和 `ObliviousOracle` 。

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a>輸入

### <a name="ancillaoracle--deterministicstateoracle"></a>ancillaOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

狀態準備 oracle $A $ 屬於 `DeterministicStateOracle` 註冊 $a $ 的型別。


### <a name="signaloracle--obliviousoracle"></a>signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

型別為的 oracle $U $ `ObliviousOracle` ，其合作于 register $a，s $。



## <a name="output--obliviousoracle"></a>輸出： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Oracle $O = UA $ of 型別 `ObliviousOracle` 。

## <a name="see-also"></a>另請參閱

- [Oracle. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Oracle. ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)