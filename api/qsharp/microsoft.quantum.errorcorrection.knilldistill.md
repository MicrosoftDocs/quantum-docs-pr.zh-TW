---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853108"
---
# <a name="knilldistill-operation"></a>KnillDistill 操作

命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


實行 Knill 魔術 state 公司演算法。

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>描述

假設有15份魔術州 $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket \end{align} 的複本 {1} ，$ $ 會產生一個較高品質的複本。

## <a name="input"></a>輸入

### <a name="roughmagic--qubit"></a>roughMagic： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]

有十五個量子位的暫存器，其中包含魔術州的大約複本。 在此公司程式的應用程式中， `roughMagic[0]` 將會包含一個較高品質的複製，而且註冊程式的其餘部分將會重設為 $ \ket{00\cdots 0} $ 狀態。



## <a name="output--bool"></a>Output： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果為 `true` ，則程式會成功，且應接受較高品質的複製。 如果為 `false` ，則程式失敗，且暫存器的狀態應視為未定義。

## <a name="remarks"></a>備註

我們遵循 Knill 演算法。
不過，目前的執行方式不太理想，因為它使用太多量子位。
魔術狀態會插入此常式中，在此情況下會有更好的通訊協定。

## <a name="references"></a>參考資料

- [Knill](https://arxiv.org/abs/quant-ph/0402171)