---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698039"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse 操作

命名空間： [Microsoft. 量子. 環境](xref:Microsoft.Quantum.Environment)

包： [](https://nuget.org/packages/)


傳回目前可供使用的量子位數目。

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>輸出： [Int](xref:microsoft.quantum.lang-ref.int)

可以在語句中配置的量子位數目 `using` 。
如果正在使用的目的電腦未提供此資訊，則 `-1` 會傳回。

## <a name="see-also"></a>另請參閱

- [GetQubitsAvailableToBorrow。](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)