---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854296"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState 函式

命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)

封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)


傳回準備指定混合狀態之淨化的作業。
「Purified 混合狀態」指的是由係數 {pi} 所指定的表單 | ψ⟩ = Σi √ pi | i ⟩ | garbagei ⟩的狀態。 此表單的狀態可以縮減為混合狀態ρ≔ pi | i ⟩⟨ i |藉由追蹤「垃圾」註冊 (也就是在計算基礎中為對角的混合狀態) 。

https://arxiv.org/pdf/1805.03662.pdf?page=15如需進一步討論，請參閱。

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>描述

使用量子 ROM 技術來代表指定的密度矩陣，並以狀態準備作業傳回該標記法。

尤其是，假設有一個 $N $ 係數 $ \ Alpha_j $ 的清單，此函式會傳回使用量子 ROM 技術的作業，以準備近似值 $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ （混合狀態 $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1-1} \ frac {| Alpha_j |}{\ sum_k | \ Alpha_k |}\ket{j}\bra{j}、\end{align} $ $，其中每個 $p _j $ 是指定係數 $ \ Alpha_j $ 的近似值，例如 $ $ \begin{align} \left |p_j-\frac{| \ Alpha_j |}{\ sum_k | \ Alpha_k |}每個 $j $ 的 \le \frac{\epsilon}{N} \end{align} $ $。

傳遞索引暫存器和垃圾量子位註冊時，一開始在 state $ \ket {0} \ket{00\cdots 0} 中，傳回的作業會將兩個暫存器準備入淨化 of $ \tilde \rho $、$ $ \begin{align} \ sum_ {j = 0} ^ {n-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}、\end{align} $ $，以便重設和解除配置垃圾註冊制定在目標錯誤 $ \epsilon $ 中所需的準備工作。

## <a name="input"></a>輸入

### <a name="targeterror--double"></a>targetError： [Double](xref:microsoft.quantum.lang-ref.double)

目標錯誤 $ \epsilon $。


### <a name="coefficients--double"></a>係數： [Double](xref:microsoft.quantum.lang-ref.double)[]

$N $ 係數的陣列，指定基礎狀態的機率。
負號 $-\ Alpha_j $ 將被視為正 $ | \ Alpha_j | $。



## <a name="output--mixedstatepreparation"></a>輸出： [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

一種作業，會將 $ \tilde \rho $ 做為淨化的聯結，以做為聯合索引和垃圾登錄的。

## <a name="example"></a>範例

下列程式碼片段會準備 $ 3 $-量子位 state $ \rho = \ sum_ {j = 0} ^ {4} \frac{| Alpha_j |} 的淨化{\ sum_k | \ Alpha_k |}\ket{j}\bra{j} $，其中 $ \vec\Alpha = (1.0、2.0、3.0、4.0、5.0) $，而目標錯誤為 $10 ^ {-3} $：

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a>備註

提供給這項作業的係數會以1個標準的形式正規化，讓係數一律視為描述有效的類別機率分佈。

## <a name="references"></a>參考資料

- 使用線性 T 複雜度編碼 Spectra 量子線路中的電子 Ryan Babbush、Craig Gidney、Dominic W. Berry、Nathan Wiebe、Jarrod McClean、Zitec Paler、奧斯丁 Fowler、Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>另請參閱

- [PurifiedMixedStateWithData。](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)