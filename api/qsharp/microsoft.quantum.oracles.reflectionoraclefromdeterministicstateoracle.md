---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700198"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle 函式

命名空間： [oracle](xref:Microsoft.Quantum.Oracles)

包： [](https://nuget.org/packages/)


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