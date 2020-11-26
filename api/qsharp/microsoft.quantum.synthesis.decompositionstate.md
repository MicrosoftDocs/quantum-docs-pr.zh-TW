---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: cd2a55013f1232d4158dd6c33143b7cf6c0aafbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203190"
---
# <a name="decompositionstate-user-defined-type"></a>DecompositionState 使用者定義型別

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


根據變數索引進行分解時的狀態

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a>命名專案

### <a name="perm--int"></a>為永久： [Int](xref:microsoft.quantum.lang-ref.int)[]


### <a name="lfunctions--bigintint"></a>Lfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []


### <a name="rfunctions--bigintint"></a>Rfunctions： ([BigInt](xref:microsoft.quantum.lang-ref.bigint)，[Int](xref:microsoft.quantum.lang-ref.int)) []



## <a name="description"></a>描述

狀態會保留目前的排列，以及左側控制的閘道目前產生的函式，以及右邊的控制管制。