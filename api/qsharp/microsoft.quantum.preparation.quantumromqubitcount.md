---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210398"
---
# <a name="quantumromqubitcount-function"></a>QuantumROMQubitCount 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> QuantumROMQubitCount 已被取代。 請改用 <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements>。

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