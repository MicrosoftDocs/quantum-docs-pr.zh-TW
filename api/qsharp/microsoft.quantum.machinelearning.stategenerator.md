---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700259"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator 使用者定義型別

命名空間： [MachineLearning](xref:Microsoft.Quantum.MachineLearning)

包： [](https://nuget.org/packages/)


描述準備指定輸入至連續分類器的作業。

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>命名專案

### <a name="nqubits--int"></a>NQubits： [Int](xref:microsoft.quantum.lang-ref.int)

已定義編碼輸入的量子位數目。
### <a name="prepare--littleendian--unit-adj--ctl"></a>準備： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl

這項作業會在量子位的位元組由小到大登錄上準備編碼的輸入 `NQubits` 。