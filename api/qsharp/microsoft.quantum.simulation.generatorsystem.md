---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858417"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem 使用者定義型別

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


代表 es 的集合 `GeneratorIndex` 。

我們會使用單一索引整數逐一查看此集合，並假設為已知的集合大小。

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>備註

您 `GeneratorSystem` 可以使用函數輕鬆地定義的實例 <xref:microsoft.quantum.arrays.lookupfunction> 。

## <a name="see-also"></a>另請參閱

- [LookupFunction。](xref:Microsoft.Quantum.Arrays.LookupFunction)