---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853239"
---
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow 操作

命名空間： [Microsoft. 量子. 環境](xref:Microsoft.Quantum.Environment)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回目前可供借用的量子位數目。

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

可以借用且不會配置為語句一部分的量子位數目 `borrowing` 。
如果正在使用的目的電腦未提供此資訊，則 `-1` 會傳回。

## <a name="see-also"></a>另請參閱

- [GetQubitsAvailableToUse。](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)