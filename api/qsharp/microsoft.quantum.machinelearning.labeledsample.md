---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846970"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample 使用者定義型別

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


範例，其標記為該範例所屬的類別。

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>命名專案

### <a name="features--double"></a>功能： [Double](xref:microsoft.quantum.lang-ref.double)[]

給定範例的特徵向量。
### <a name="label--int"></a>標籤： [Int](xref:microsoft.quantum.lang-ref.int)

此範例所屬類別的整數標籤。