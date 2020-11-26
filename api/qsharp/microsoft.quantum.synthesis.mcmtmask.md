---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203007"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask 使用者定義型別

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


一種類型，代表多重控制的多目標 Toffoli 閘道。

第一個整數是控制行的位元遮罩。  設定的位索引會對應至控制行索引。

第二個整數是目標行的位元遮罩。  設定對應至目標行索引的位索引。

這兩個整數的位索引必須相鄰。

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>命名專案

### <a name="controlmask--int"></a>ControlMask： [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask： [Int](xref:microsoft.quantum.lang-ref.int)

