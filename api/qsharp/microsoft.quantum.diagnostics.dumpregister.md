---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829223"
---
# <a name="dumpregister-function"></a>DumpRegister 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傾印目前目的電腦與指定量子位相關聯的狀態。

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>輸入

### <a name="location--t"></a>位置： t

提供有關何處可以產生狀態傾印的資訊。


### <a name="qubits--qubit"></a>量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

要報告的量子位清單。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

無。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

這個方法可讓您將與指定量子位狀態相關聯的資訊傾印到檔案或其他位置。
實際產生的資訊和的語義 `location` 都是每個目的電腦的特定資訊。 不過，將空的元組提供為位置 (`()`) 通常表示要產生主控台的輸出。

對於分散為量子開發工具組一部分的本機完整狀態模擬器，這個方法預期會有檔案路徑的字串，而檔案的路徑將會寫入指定的量子位的狀態 (亦即，對應子系統的 wave 函數) 為複數的一維陣列，其中每個專案都代表測量相對應狀態之機率的 amplitudes。
如果指定的量子位是以其他量子位纏結，而且其狀態無法分隔，它只會報告量子位為纏結。