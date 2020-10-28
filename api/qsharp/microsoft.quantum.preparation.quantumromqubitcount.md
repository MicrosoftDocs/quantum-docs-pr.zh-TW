---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700411"
---
# <a name="quantumromqubitcount-function"></a>QuantumROMQubitCount 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

包： [](https://nuget.org/packages/)


傳回必須配置給所傳回之作業的量子位總數 `QuantumROM` 。

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a>輸入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目標錯誤 $ \epsilon $。


### <a name="ncoeffs--int"></a>nCoeffs： [Int](xref:microsoft.quantum.lang-ref.int)

中指定的係數數目 `QuantumROM` 。



## <a name="output--intintint"></a>輸出： ([int](xref:microsoft.quantum.lang-ref.int)， ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) # A3

## <a name="first-parameter"></a>第一個參數

元組， `(x,(y,z))` 其中 `x = y + z` 是配置的量子位總數， `y` 是註冊的量子位數目 `LittleEndian` ，而 `z` 是垃圾量子位的數目。