---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701146"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask 使用者定義型別

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)


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

