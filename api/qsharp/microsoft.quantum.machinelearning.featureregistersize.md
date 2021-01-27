---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848434"
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