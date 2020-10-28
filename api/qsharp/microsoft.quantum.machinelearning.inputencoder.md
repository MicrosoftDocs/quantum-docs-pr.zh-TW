---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697231"
---
# <a name="inputencoder-function"></a>InputEncoder 函式

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


如果有一組係數和容錯，則會傳回狀態準備作業，將每個係數準備為計算基礎狀態的對應波幅。

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>輸入

### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

要編碼為輸入狀態的係數。



## <a name="output--stategenerator"></a>輸出： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

一種狀態準備作業，可將指定的係數準備為指定之暫存器的輸入狀態。