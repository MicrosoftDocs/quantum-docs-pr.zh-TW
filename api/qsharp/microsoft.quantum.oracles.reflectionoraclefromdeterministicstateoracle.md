---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842516"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle 函式

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


從 oracle 結構反映指定狀態的反映。

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>描述

假設有一個由單一矩陣 $O $ 所表示的決定性狀態準備 oracle，則此函式的結果為 oracle，可針對 oracle $O $; 所準備的狀態 $ \ket{\psi} $ 套用反映也就是說，state $ \ket{\psi} $，例如 $O \ket {0} = \ket{\psi} $。

## <a name="input"></a>輸入

### <a name="oracle--deterministicstateoracle"></a>oracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

準備狀態 $ \ket{\psi} $ 複本的 oracle。



## <a name="output--reflectionoracle"></a>輸出： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

反映狀態 $ \ket{\psi} $ 的 oracle。

## <a name="see-also"></a>另請參閱

- [Oracle. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Oracle. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)