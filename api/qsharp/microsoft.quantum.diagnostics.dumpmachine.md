---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853409"
---
# <a name="dumpmachine-function"></a>DumpMachine 函式

命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傾印目前目的電腦的狀態。

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>輸入

### <a name="location--t"></a>位置： t

提供有關如何產生機器傾印的資訊。



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)

無。

## <a name="type-parameters"></a>類型參數

### <a name="t"></a>不要



## <a name="remarks"></a>備註

這個方法可讓您將目的電腦目前狀態的相關資訊傾印到檔案或其他位置。
實際產生的資訊和的語義 `location` 都是每個目的電腦的特定資訊。 不過，將空的元組提供為位置 (`()`) ，或只是省略 `location` 參數通常表示要產生主控台的輸出。

對於分散為量子開發工具組一部分的本機完整狀態模擬器，這個方法預期會有檔案路徑的字串，而檔案的路徑會將 wave 函式寫入為一維的複數陣列，其中每個元素都代表測量相對應狀態之機率的 amplitudes。