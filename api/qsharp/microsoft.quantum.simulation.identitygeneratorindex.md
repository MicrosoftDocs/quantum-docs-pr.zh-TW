---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: b389ca1e0737463e6ccd5ce885b849c6b32d65d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844331"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回與零 Hamiltonian （對應至身分識別演進作業）一致的產生器索引 `H = 0` 。

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>輸入

### <a name="idxterm--int"></a>idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)

此輸入會被忽略，而且是為了與使用者定義型別一致而定義的 <xref:microsoft.quantum.simulation.generatorsystem> 。



## <a name="output--generatorindex"></a>輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

代表 Hamiltonian $H = $0 下演進的產生器索引。