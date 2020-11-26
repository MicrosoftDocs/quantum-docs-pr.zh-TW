---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196407"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


傳回編碼特定功能向量所需的量子位數目。

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>輸入

### <a name="sample--double"></a>範例： [Double](xref:microsoft.quantum.lang-ref.double)[]

要編碼成量子位註冊的範例功能向量。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

編碼為量子位暫存器所需的大小 `sample` ，以量子位數表示。