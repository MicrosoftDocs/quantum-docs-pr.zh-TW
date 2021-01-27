---
uid: Microsoft.Quantum.Synthesis.Extended
title: 擴充函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855480"
---
# <a name="extended-function"></a>擴充函數

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以反轉係數擴充頻譜

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>輸入

### <a name="spectrum--int"></a>頻譜： [Int](xref:microsoft.quantum.lang-ref.int)[]

光譜系數



## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]

後面接著反向複製的係數

## <a name="example"></a>範例

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```