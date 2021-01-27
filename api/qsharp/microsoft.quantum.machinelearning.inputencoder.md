---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852948"
---
# <a name="inputencoder-function"></a>InputEncoder 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


如果有一組係數和容錯，則會傳回狀態準備作業，將每個係數準備為計算基礎狀態的對應波幅。

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>輸入

### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

要編碼為輸入狀態的係數。



## <a name="output--stategenerator"></a>輸出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

一種狀態準備作業，可將指定的係數準備為指定之暫存器的輸入狀態。