---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698034"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>_ExtractLogicalQubitFromSteaneCode 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [](https://nuget.org/packages/)


症狀測量和內嵌的反向。

$X $-和 $Z $-stabilizers 不會平均處理，這是因為編碼電路的特殊選擇。
這種不對稱會導致不同的症狀解壓縮常式。
您可以直接在程式碼狀態上測量多量子位 Pauli 運算子來測量症狀，但是針對公司用途，邏輯量子位會傳回單一量子位，但在此情況下，不需要進一步 ancillas 即可完成這些症狀測量。

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>輸入

### <a name="code--logicalregister"></a>程式碼： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)、[int](xref:microsoft.quantum.lang-ref.int)、[int](xref:microsoft.quantum.lang-ref.int)) 

邏輯量子位以及一對 $X $-症狀和 $Z $-症狀的整數。
它們代表程式碼量子位的索引，其中單一 $X $ 或 $Z $-錯誤會造成測量的症狀。

## <a name="remarks"></a>備註

請注意，這項作業不會標示為 `internal` ，因為單元測試會直接相依于這項作業。 基於未來的改進，單元測試應該重構，才能直接相依于公用 callables。

> [!WARNING]
> 此常式是針對 Steane 的7量子位程式碼的特定編碼電路量身打造;如果已修改編碼電路，則可能必須以不同的方式解釋症狀結果。