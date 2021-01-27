---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827792"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse 操作

命名空間： [Microsoft. 量子. 環境](xref:Microsoft.Quantum.Environment)

套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


傳回目前可供使用的量子位數目。

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

可以在語句中配置的量子位數目 `using` 。
如果正在使用的目的電腦未提供此資訊，則 `-1` 會傳回。

## <a name="see-also"></a>另請參閱

- [GetQubitsAvailableToBorrow。](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)