---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830977"
---
# <a name="_prepareentangledstate-operation"></a>_prepareEntangledState 操作

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


假設有兩個暫存器，請在個別暫存器上的每一對量子位之間準備充分纏結狀態。
所有量子位都必須以 | 0 ⟩狀態開始。

結果是，每個註冊程式的對應量子位都位於 $ \bra{\ Beta_ {00} } \ket{\ Beta_ {00} } $。

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="left--qubit"></a>左方： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cdots 0} $ 狀態中的量子位陣列


### <a name="right--qubit"></a>right： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cdots 0} $ 狀態中的量子位陣列



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

