---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: b6f3fe0ececc58d86b916841c513377fbcb59054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699043"
---
# <a name="decomposeintotimestepsca-function"></a>DecomposeIntoTimeStepsCA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

包： [](https://nuget.org/packages/)


> [!WARNING]
> DecomposeIntoTimeStepsCA 已被取代。 請改用 <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA>。



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="nsteps--int"></a>nSteps： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--intdoublet--unit-adj--ctl"></a>op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl




### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--doublet--unit-adj--ctl"></a>輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

