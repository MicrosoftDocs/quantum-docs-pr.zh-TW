---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853680"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


獲得成功機率之後，會傳回一則具有指定機率的單一利利實驗。

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>輸入

### <a name="successprobability--double"></a>successProbability： [Double](xref:microsoft.quantum.lang-ref.double)

應該傳回的機率 `true` 。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 具有機率 `successProbability` 和機率 `false` `1.0 - successProbability` 。

## <a name="example"></a>範例

下列 Q # 程式碼片段範例會從偏誤的硬幣中翻轉：

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```