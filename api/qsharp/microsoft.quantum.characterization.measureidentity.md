---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216110"
---
# <a name="measureidentity-operation"></a>MeasureIdentity 操作

命名空間： [Microsoft 量子. 特性](xref:Microsoft.Quantum.Characterization)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


測量量子位註冊上的身分識別運算子。

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>輸入

### <a name="register--qubit"></a>register： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要測量的註冊。



## <a name="output--__invalidresult__"></a>輸出：__無效 <Result>__

結果值 `Zero` 。

## <a name="remarks"></a>備註

由於 $ \boldone $ 只有 eigenvalue $1 $，而且沒有負 eigenvalue，因此此作業一律 `Zero` 會傳回，對應至 eigenvalue $ + 1 = (-1) ^ $0，而不會造成的狀態折迭 `register` 。

這項作業本身本身並沒有用，但在流程 tomography 的內容中很有用，因為它提供了量子進程的追蹤保留相關資訊。
尤其是具有失真測量的目的電腦，應該將此作業取代為實際的 $ \boldone $ 度量。