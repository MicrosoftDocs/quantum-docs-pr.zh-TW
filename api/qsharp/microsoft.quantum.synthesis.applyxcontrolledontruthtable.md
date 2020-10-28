---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701074"
---
# <a name="applyxcontrolledontruthtable-operation"></a>ApplyXControlledOnTruthTable 操作

命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)

包： [](https://nuget.org/packages/)


@"microsoft.quantum.intrinsic.x" `target` 如果布耳函數 `func` 針對中的傳統指派評估為 true，則會在上套用運算 `controlRegister` 。

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>描述

作業會執行單一作業 \begin{align} U\ket {x} \ ket {y} = \ket{x}\ket{y \oplus f (x) } \end{align}，其中 $x $ 和 $y $ `controlRegister` 分別代表和 `target` 。

布耳函數 $f $ 會以大整數的形式表示為事實資料表。
例如，在三個輸入上的多數函數會以 bitstring 表示 `11101000` ，其中最重要的位會 `1` 對應至輸入指派 `(1, 1, 1)` ，而最小的位會 `0` 對應至輸入指派 `(0, 0, 0)` 。
它可以使用十六進位標記法中的大整數來表示， `0xE8L` 或以 `232L` 十進位標記法表示。  `L`尾碼表示常數的型別為 `BigInt` 。
您也可以在 [事實資料表 kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)中找到此標記法的詳細資料。

執行會使用和網 @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" 關。

## <a name="input"></a>輸入

### <a name="func--bigint"></a>func： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

以大整數表示的布林事實資料表


### <a name="controlregister--qubit"></a>controlRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

註冊控制項量子位


### <a name="target--qubit"></a>目標： [量子位](xref:microsoft.quantum.lang-ref.qubit)

目標量子位



## <a name="output--unit"></a>輸出： [單位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>參考

- [*N. Schuch* 、 *J Siewert* 、PRL 91、no. 027902、2003、arXiv： quant-ph/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken* 、 *聖馬丁 Roetteler* 、arXiv：2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>另請參閱

- [ApplyXControlledOnTruthTableWithCleanTarget。](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)