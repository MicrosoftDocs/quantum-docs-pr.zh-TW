---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701070"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>ApplyXControlledOnTruthTableWithCleanTarget 操作

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)


@"microsoft.quantum.intrinsic.x" `target` 如果布耳函數 `func` 針對中的傳統指派評估為 true，則會在上套用運算 `controlRegister` 。

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>描述

這項作業會執行特殊案例 @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" ，在此案例中，目標量子位已知為 $ \ket {0} $ 狀態。

執行會使用和網 @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" 關。  Adjoint 作業的實作為優化，並使用以度量為基礎的 uncomputation。

## <a name="input"></a>輸入

### <a name="func--bigint"></a>func： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

以大整數表示的布林事實資料表


### <a name="controlregister--qubit"></a>controlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊控制項量子位


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

目標量子位 (必須是 $ \ket {0} $ state) 



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另請參閱

- [ApplyXControlledOnTruthTable。](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)