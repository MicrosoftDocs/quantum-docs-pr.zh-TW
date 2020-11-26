---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192956"
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