---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701063"
---
# <a name="decompositionstate-user-defined-type"></a>DecompositionState 使用者定義型別

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)


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