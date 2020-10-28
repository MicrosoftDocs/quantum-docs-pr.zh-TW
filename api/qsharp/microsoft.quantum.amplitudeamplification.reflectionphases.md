---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700094"
---
# <a name="reflectionphases-user-defined-type"></a>ReflectionPhases 使用者定義型別

命名空間： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [](https://nuget.org/packages/)


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