---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700871"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex 函式

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


傳回與零 Hamiltonian （對應至身分識別演進作業）一致的產生器索引 `H = 0` 。

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>輸入

### <a name="idxterm--int"></a>idxTerm： [Int](xref:microsoft.quantum.lang-ref.int)

此輸入會被忽略，而且是為了與使用者定義型別一致而定義的 <xref:microsoft.quantum.simulation.generatorsystem> 。



## <a name="output--generatorindex"></a>輸出： [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

代表 Hamiltonian $H = $0 下演進的產生器索引。