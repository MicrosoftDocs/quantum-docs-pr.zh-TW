---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700514"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


傳回編碼特定功能向量所需的量子位數目。

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>輸入

### <a name="sample--double"></a>範例： [Double](xref:microsoft.quantum.lang-ref.double)[]

要編碼成量子位註冊的範例功能向量。



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

編碼為量子位暫存器所需的大小 `sample` ，以量子位數表示。