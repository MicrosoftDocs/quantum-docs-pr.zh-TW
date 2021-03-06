---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852400"
---
# <a name="noop-operation"></a>NoOp 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


在引數上 (非 op) 執行身分識別作業。

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

這項作業會接受任何類型的值，而且不會對它執行任何動作。
只要預期的是作業類型的輸入，但不應該採取任何動作，這項功能就很有用。
比方說，如果特定錯誤更正問題指出未發生任何錯誤， `NoOp<Qubit[]>` 則可能是正確的修復程式。
同樣地，如果作業預期狀態準備程式做為輸入， `NoOp<Qubit[]>` 就可以用來準備狀態 $ \ket{0 \cdots 0} $。

## <a name="input"></a>輸入

### <a name="input--t"></a>輸入： t

要忽略的值。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

在幾乎所有情況下，必須明確指定的型別參數 `NoOp` 。 例如，與 `NoOp<Qubit>` 相同 <xref:microsoft.quantum.intrinsic.i> 。

## <a name="see-also"></a>另請參閱

- [... I](xref:Microsoft.Quantum.Intrinsic.I)