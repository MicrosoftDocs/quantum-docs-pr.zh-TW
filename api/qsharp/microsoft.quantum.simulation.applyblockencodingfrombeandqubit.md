---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingFromBEandQubit
title: ApplyBlockEncodingFromBEandQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingFromBEandQubit
qsharp.summary: Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding
ms.openlocfilehash: d11c5bd8a33fc5dfc9ed3aa374c9c53afe286e24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700175"
---
# <a name="applyblockencodingfrombeandqubit-operation"></a>ApplyBlockEncodingFromBEandQubit 操作

命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)

包： [](https://nuget.org/packages/)


轉換 ( # B1 LittleEndian，量子位 [] ) => ( # A4 是對 BlockEncoding 進行的形容詞和 Ctl) 

```qsharp
operation ApplyBlockEncodingFromBEandQubit (op : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl), auxiliary : Qubit[], system : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="op--littleendianqubit--unit-adj--ctl"></a>op： ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) => [單位](xref:microsoft.quantum.lang-ref.unit) 調整 + Ctl




### <a name="auxiliary--qubit"></a>輔助： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="system--qubit"></a>system： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

