---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699656"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool 操作

命名空間： [Microsoft. 量子](xref:Microsoft.Quantum.Random)

包： [](https://nuget.org/packages/)


獲得成功機率之後，會傳回一則具有指定機率的單一利利實驗。

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>輸入

### <a name="successprobability--double"></a>successProbability： [Double](xref:microsoft.quantum.lang-ref.double)

應該傳回的機率 `true` 。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

`true` 具有機率 `successProbability` 和機率 `false` `1.0 - successProbability` 。