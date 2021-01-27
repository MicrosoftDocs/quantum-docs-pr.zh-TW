---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844993"
---
# <a name="applyifca-operation"></a>ApplyIfCA 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


針對傳統位套用條件的單一作業。

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

指定作業 `op` 和位值時 `bit` ， `op` 如果是，則 `target` 會套用至 `bit` `true` 。 如果 `false` 為，則不會發生任何事 `target` 。
尾碼 `CA` 表示要套用的作業是單一 (可控制和 adjointable) 。

## <a name="input"></a>輸入

### <a name="op--t--unit--is-adj--ctl"></a>op： t => [單位](xref:microsoft.quantum.lang-ref.unit)  為形容詞 + Ctl

有條件地套用的作業。


### <a name="bit--bool"></a>bit： [Bool](xref:microsoft.quantum.lang-ref.bool)

此為布林值，可控制是否要套用 op。


### <a name="target--t"></a>目標： t

要套用作業的輸入。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要

要有條件地套用之作業的輸入類型。

## <a name="example"></a>範例

下列程式會將量子位登錄為計算基礎狀態，並以指定為值陣列的傳統位字串表示 `Bool` ：

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a>另請參閱

- [Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)