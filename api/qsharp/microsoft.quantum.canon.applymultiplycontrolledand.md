---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: ac3972287d55ed2df85e1d88510918cc5202c711
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844848"
---
# <a name="applymultiplycontrolledand-operation"></a>ApplyMultiplyControlledAnd 操作

命名空間： [Canon](xref:Microsoft.Quantum.Canon)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


假設目標量子位已初始化為0，則會執行多個控制的 Toffoli 閘道。  Adjoint 作業會假設目標量子位將重設為0。

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a>輸入

### <a name="controls--qubit"></a>控制項： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

控制項量子位


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

目標量子位



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

