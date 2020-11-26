---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases 使用者定義型別
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191341"
---
# <a name="reflectionphases-user-defined-type"></a>ReflectionPhases 使用者定義型別

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


以振幅放大的部分反射順序的階段。

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>命名專案

### <a name="aboutstart--double"></a>AboutStart： [Double](xref:microsoft.quantum.lang-ref.double)[]

關於開始狀態之反映的階段陣列。
### <a name="abouttarget--double"></a>AboutTarget： [Double](xref:microsoft.quantum.lang-ref.double)[]

有關目標狀態之反映的階段陣列。

## <a name="remarks"></a>備註

這兩個數組的長度必須相等。 請注意，在許多情況下，有關目標狀態的開始狀態和最後一個階段的第一個階段會引進全域階段轉移，而且可以設定為 $0 $。