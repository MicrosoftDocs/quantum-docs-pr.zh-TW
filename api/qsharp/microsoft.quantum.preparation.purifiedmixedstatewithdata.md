---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229948"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回作業，此作業會準備指定混合狀態的淨化，並以代表指定資料集合的暫存器纏結。
「具有資料的 purified 混合狀態」指的是表單Σi √ pi | i ⟩ | xi ⟩ | garbagei ⟩的狀態，其中每個 xi 都是 bitstring 編碼的額外資料 | i ⟩。

https://arxiv.org/pdf/1805.03662.pdf?page=15如需進一步討論，請參閱。

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>描述

使用量子 ROM 技術來代表指定的密度矩陣，並以狀態準備作業傳回該標記法。

尤其是，假設有一份 $N $ 係數 $ \ Alpha_j $，以及 _與每個係數相關聯的 bitstring $ \vec{x} j $。此函式會傳回使用量子 ROM 技術的作業，以準備近似值 $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {n-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ （混合狀態 $ $ \begin{align} \rho = \sum_{j = 0} ^ {n-1} \ frac {| Alpha_j |}{\ sum_k | \ Alpha_k |}\ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}、\end{align} $ $，其中每個 $p _j $ 是指定係數 $ \ Alpha_j $ 的近似值，例如 $ $ \begin{align} \left |p_j-\frac{| \ Alpha_j |}{\ sum_k | \ Alpha_k |}每個 $j $ 的 \le \frac{\epsilon}{N} \end{align} $ $。

傳遞索引暫存器和垃圾量子位註冊時，一開始在 state $ \ket {0} \ket{00\cdots 0} 中，傳回的作業會將兩個暫存器準備入淨化 of $ \tilde \rho $、$ $ \begin{align} \ sum_ {j = 0} ^ {n-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}、\end{align} $ $，以便重設和解除配置垃圾註冊制定在目標錯誤 $ \epsilon $ 中所需的準備。

## <a name="input"></a>輸入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目標錯誤 $ \epsilon $。


### <a name="coefficients--doublebool"></a>係數： ([Double](xref:microsoft.quantum.lang-ref.double)，[Bool](xref:microsoft.quantum.lang-ref.bool)[] ) []

$N $ 係數的陣列，用來指定基礎狀態的機率，以及與每個係數相關聯的 bitstring $ \vec{x} _j $。
負號 $-\ Alpha_j $ 將被視為正 $ | \ Alpha_j | $。



## <a name="output--mixedstatepreparation"></a>輸出： [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

一種作業，會將 $ \tilde \rho $ 做為淨化的聯結，以做為聯合索引和垃圾登錄的。

## <a name="remarks"></a>備註

提供給這項作業的係數會以1個標準的形式正規化，讓係數一律視為描述有效的類別機率分佈。

## <a name="references"></a>參考

- 使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>另請參閱

- [PurifiedMixedState。](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)