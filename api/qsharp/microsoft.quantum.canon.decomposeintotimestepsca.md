---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: aa004098cbc805126109d3356f0f6550b85cd60b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840722"
---
# <a name="decomposeintotimestepsca-function"></a>DecomposeIntoTimeStepsCA 函式

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> DecomposeIntoTimeStepsCA 已被取代。 請改用 <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA>。



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>輸入

### <a name="nsteps--int"></a>nSteps： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--intdoublet--unit--is-adj--ctl"></a>op： ([Int](xref:microsoft.quantum.lang-ref.int)，[Double](xref:microsoft.quantum.lang-ref.double)，t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl




### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--doublet--unit--is-adj--ctl"></a>輸出： ([雙精度浮點數](xref:microsoft.quantum.lang-ref.double)) => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

