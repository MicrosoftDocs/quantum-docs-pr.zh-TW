---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: cc70cc409cb472a747899838d3a9ad2d78f6b5ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827700"
---
# <a name="applybitflipencoder-operation"></a>ApplyBitFlipEncoder 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


私用作業，用來同時執行位翻轉編碼器和解碼器。

請注意，此編碼器可利用就地連貫的復原，在這種情況下，它會「造成」的初始狀態所描述的錯誤 `auxQubits` 。
尤其是，如果 `auxQubits` 最初是在 state $ \ket {10} $ 中，這會導致在編碼的量子位上 $X _1 $ error。

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>輸入

### <a name="coherentrecovery--bool"></a>coherentRecovery： [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="data--qubit"></a>data： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="scratch--qubit"></a>臨時： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考資料

- doi:10.1103/PhysRevA.85.044302