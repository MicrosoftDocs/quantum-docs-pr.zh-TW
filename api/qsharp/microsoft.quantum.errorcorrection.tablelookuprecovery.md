---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697887"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery 函式

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


針對指定之量子位暫存器上的 Pauli 作業，此函式會傳回類型的物件， `RecoveryFn` 其中包含執行與特定 Pauli 作業陣列相關之資料表查閱解碼所需的所有資訊。

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>輸入

### <a name="table--pauli"></a>table： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

在指定量子位暫存器上操作的 Pauli 作業資料表



## <a name="output--recoveryfn"></a>輸出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

型別為的物件 `RecoveryFn` ，也 `Syndrome -> Pauli[]` 就是與指定的症狀陣列相關聯的對應 Pauli 更正作業。