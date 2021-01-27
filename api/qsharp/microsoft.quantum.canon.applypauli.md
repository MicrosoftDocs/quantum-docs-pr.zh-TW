---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844745"
---
# <a name="applypauli-operation"></a>ApplyPauli 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設有多量子位 Pauli 運算子，請將對應的作業套用至暫存器。

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>輸入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]

多量子位的 Pauli 運算子，以單一量子位 Pauli 運算子的陣列表示。


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊以在上套用指定的 Pauli 作業。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>範例

以下是相等的：

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

及

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```