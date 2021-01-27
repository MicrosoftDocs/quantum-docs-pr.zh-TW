---
uid: Microsoft.Quantum.Random.StandardNormalDistribution
title: StandardNormalDistribution 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: StandardNormalDistribution
qsharp.summary: Returns a normal distribution with mean 0 and variance 1.
ms.openlocfilehash: e1776339655c33516f7b3d156f1b377a0c74d250
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857804"
---
# <a name="standardnormaldistribution-function"></a>StandardNormalDistribution 函式

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回具有 mean 0 和變異數1的一般分佈。

```qsharp
function StandardNormalDistribution () : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="output--continuousdistribution"></a>輸出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>範例

下列範例會從標準一般分佈中繪製10個樣本：

```qsharp
let samples = DrawMany((StandardNormalDistribution())::Sample, 10, ());
```

## <a name="see-also"></a>另請參閱

- [NormalDistribution。](xref:Microsoft.Quantum.Random.NormalDistribution)