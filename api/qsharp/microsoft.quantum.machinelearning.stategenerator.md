---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854881"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator 使用者定義型別

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

封裝： [MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


描述準備指定輸入至連續分類器的作業。

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>命名專案

### <a name="nqubits--int"></a>NQubits： [Int](xref:microsoft.quantum.lang-ref.int)

已定義編碼輸入的量子位數目。
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>準備： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

這項作業會在量子位的位元組由小到大登錄上準備編碼的輸入 `NQubits` 。