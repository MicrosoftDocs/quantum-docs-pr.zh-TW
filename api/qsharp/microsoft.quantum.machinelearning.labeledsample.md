---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697683"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample 使用者定義型別

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


範例，其標記為該範例所屬的類別。

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>命名專案

### <a name="features--double"></a>功能： [Double](xref:microsoft.quantum.lang-ref.double)[]

給定範例的特徵向量。
### <a name="label--int"></a>標籤： [Int](xref:microsoft.quantum.lang-ref.int)

此範例所屬類別的整數標籤。