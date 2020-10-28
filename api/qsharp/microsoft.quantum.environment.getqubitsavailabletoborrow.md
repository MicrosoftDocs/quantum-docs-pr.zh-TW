---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698042"
---
# <a name="getqubitsavailabletoborrow-operation"></a>GetQubitsAvailableToBorrow 操作

命名空間： [Microsoft. 量子. 環境](xref:Microsoft.Quantum.Environment)

包： [](https://nuget.org/packages/)


傳回目前可供借用的量子位數目。
這包括未使用的量子位;也就是說，這包括所傳回的量子位 `GetQubitsAvailableToUse` 。

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

可以在語句中配置的量子位數目 `borrowing` 。
如果正在使用的目的電腦未提供此資訊，則 `-1` 會傳回。

## <a name="see-also"></a>另請參閱

- [GetQubitsAvailableToUse。](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)