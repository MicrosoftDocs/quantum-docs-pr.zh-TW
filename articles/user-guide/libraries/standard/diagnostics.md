---
title: 標準程式庫中的診斷 Q#
description: 瞭解在 Q# 量副程式中用來攔截錯誤或錯誤的標準程式庫中的診斷功能和作業。
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1ab9b77c7536a1860064110810371d3a68e95b40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690843"
---
# <a name="diagnostics"></a>診斷 #

就像傳統開發一樣，要能夠診斷量副程式中的錯誤和錯誤是很重要的。
Q#標準程式庫提供各種不同的方式來確保量副程式的正確性，如中所述 <xref:microsoft.quantum.guide.testingdebugging> 。
大致上來說，這項支援的形式為函式和作業，可指示目的電腦為主機程式或開發人員提供額外的診斷資訊，或強制執行函式或作業呼叫所表示的條件和非變異的正確性。

## <a name="machine-diagnostics"></a>機器診斷 ##

您可以使用函 <xref:Microsoft.Quantum.Intrinsic.Message> 式以電腦相依的方式來記錄訊息，以取得有關傳統值的診斷功能。
根據預設，這會將字串寫入主控台。
與內插字串一起使用， <xref:Microsoft.Quantum.Intrinsic.Message> 可讓您輕鬆地報告有關傳統值的診斷資訊：

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` 有簽章 `(String -> Unit)` ，但無法從內觀察發出的偵錯工具記錄訊息 Q# 。

<xref:Microsoft.Quantum.Diagnostics.DumpMachine>和 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> callables 指示目的電腦，以提供有關目前已配置之量子位的診斷資訊，或分別提供量子位的特定註冊。
每一部目的電腦都有不同的診斷資訊，以回應傾印指令。
例如， [完整狀態](xref:microsoft.quantum.machines.full-state-simulator) 模擬器目的電腦提供的主機程式具有在內部用來代表量子位註冊的狀態向量。
相較之下， [Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) 模擬器目的電腦為每個量子位提供單一的傳統位。

 若要深入瞭解 [完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器的 `DumpMachine` 輸出，請參閱 [測試和偵錯工具文章](xref:microsoft.quantum.guide.testingdebugging#dump-functions)的傾印函式一節。


## <a name="facts-and-assertions"></a>事實和判斷提示 ##

如 [測試和](xref:microsoft.quantum.guide.testingdebugging)偵測所述，可以將具有簽章或的函式或作業 `Unit -> Unit` `Unit => Unit` 分別標示為 *單元測試* 。
每個單元測試通常包含一個小的量副程式，以及一個或多個檢查該程式是否正確的條件。
這些條件可以是任一 _事實_ 的形式，它會檢查輸入的值或 _判斷_ 提示的值，以檢查傳遞給輸入的一或多個量子位的狀態。

例如， `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` 代表 $1 + 1 = $2 的數學事實，而 `AssertQubit(One, qubit)` 表示測量會傳回確定性的條件 `qubit` `One` 。
在先前的案例中，我們只會檢查指定值的正確性，但在後者中，我們必須知道量子位狀態的相關資訊，才能評估判斷提示。

Q#標準程式庫提供數個代表事實的不同函式，包括：

- <xref:Microsoft.Quantum.Diagnostics.Fact>
- <xref:Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact>
- <xref:Microsoft.Quantum.Diagnostics.NearEqualityFactC>
- <xref:Microsoft.Quantum.Diagnostics.EqualityFactI>


### <a name="testing-qubit-states"></a>測試量子位狀態 ###

在實務上，判斷提示會依賴量子機制的傳統模擬不需要遵守 [無複製定理](https://arxiv.org/abs/quant-ph/9607018)，因此我們可以在為目的電腦使用模擬器時，進行 unphysical 測量和判斷提示。
因此，我們可以在傳統模擬器上測試個別的作業，然後再于硬體上進行部署。
在不允許評估判斷提示的目的電腦上， <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 可以安全地忽略的呼叫。

更常見的情況是，作業會判斷提示 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 以指定的 Pauli 為基礎來測量指定的量子位，一律會有指定的結果。
如果判斷提示失敗，則會以指定的訊息呼叫來結束執行 `fail` 。
依預設，不會執行這項作業;可以支援的模擬器應該提供執行執行時間檢查的執行。
`AssertMeasurement` 有簽章 `((Pauli[], Qubit[], Result, String) -> ())` 。
因為 `AssertMeasurement` 是具有空的元組作為其輸出類型的函式，所以在 `AssertMeasurement` 程式內不會有呼叫的影響 Q# 。

作業函式會判斷提示 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> ，以指定的 Pauli 為基礎來測量指定的量子位，在部分容錯範圍內會有給定機率的指定結果。
容錯是加法 (例如 `abs(expected-actual) < tol`) 。
如果判斷提示失敗，則會以指定的訊息呼叫來結束執行 `fail` 。
依預設，不會執行這項作業;可以支援的模擬器應該提供執行執行時間檢查的執行。
`AssertMeasurementProbability` 有簽章 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` 。 第一個 `Double` 參數會提供所需的結果機率，而第二個則是容錯。

我們可以使用模擬器所用的傳統資訊來代表量子位的內部狀態，以進行複製，而不需要實際執行測量以測試我們的判斷提示，就可以進行一次以上的測量。
尤其是，這可讓我們瞭解在實際硬體上可能不可能發生 *不相容* 的度量的原因。

假設這 `P : Qubit => Unit` 是一項作業，目的是要在它的輸入處於狀態 $ \ket $ 時準備狀態 $ \ket{\psi} $ {0} 。
Let $ \ket{\psi '} $ 是所準備的實際狀態 `P` 。
然後，只有在 $ \ket{\psi} $ 所描述的座標軸中測量 $ \ket{\psi '} $ 時，才會傳回 $ \ket{\psi} = \ket{\psi '} $ `Zero` 。
也就是說，\begin{align} \ket{\psi} = \ket{\psi '} \text{if and only} \braket{\psi | \psi '} = 1。
\end{align} 使用在序言中定義的基本作業，我們可以直接執行測量，以傳回 `Zero` $ \ket{\psi} $ 是否為其中一個 Pauli 運算子的 eigenstate。


當 <xref:Microsoft.Quantum.Diagnostics.AssertQubit> 我們想要測試判斷提示 $ \ket{\psi} = \ket $ 時，此作業會提供特別實用的速記來進行這項操作 {0} 。
這種情況很常見，例如，當我們在釋放 ancilla 量子位至 $ \ket $ 之前，我們有 uncomputed {0} 。
{0}當我們想要判斷提示兩個狀態準備 `P` 和 `Q` 作業都準備相同的狀態，而且支援時，對 $ \ket $ 的判斷提示也很有用 `Q` `Adjoint` 。
尤其是

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

不過，更常見的情況是，我們可能無法存取與 Pauli 運算子 eigenstates 不一致的狀態判斷提示。
例如，$ \ket{\psi} = ( \ket {0} + e ^ {i \pi/8} \ket {1}) /\sqrt {2} $ 不是任何 eigenstate 運算子的 Pauli，因此我們無法用 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 來唯一判斷 state $ \ket{\psi '} $ 等於 $ \ket{\psi} $。
相反地，我們必須將判斷提示 $ \ket{\psi '} = \ket{\psi} $ 分解成可使用模擬器所支援的基本專案直接測試的假設。
若要這樣做，請將 $ \ket{\psi} = \Alpha \ket {0} + \Beta \ket {1} $ 用於複數 $ \Alpha = a \_ i r + a \_ i $ 和 $ \Beta $。
請注意，這個運算式需要四個實數 $ \{ a \_ r、 \_ i、b \_ r、b \_ i \} $ 來指定，因為每一個複數都可以表示成實數和虛數部分的總和。
不過，由於全球階段的緣故，我們可以選擇 $a \_ i = $0，因此我們只需要三個實數才能唯一指定單一量子位的狀態。

因此，我們需要指定三個彼此獨立的判斷提示，以判斷提示所預期的狀態。
我們的做法是找 `Zero` 出每個 Pauli 測量值的觀察到 $ \Alpha $ 和 $ \Beta $，然後個別判斷提示。
讓 $x $、$y $ 和 $z $ 分別為 `Result` Pauli $X $、$Y $ 和 $Z $ 度量的值。
然後，使用量子測量的可能性函數，\begin{align} \Pr (x = \texttt{Zero} |\Alpha、\Beta) & = \frac12 + a \_ r b \_ r + a \_ i b \_ i \\ \\ \Pr (y = \texttt{Zero} | \Alpha，\Beta) & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \Pr (z = \texttt{Zero} | \Alpha，\Beta) & = \frac12\left ( 1 + a \_ r ^ 2 + a \_ i ^ 2 + b r ^ 2 + \_ b \_ i ^ 2 \right) 。
\end{align}

作業會在 <xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance> 指定的 $ \Alpha $ 和 $ \Beta $ 標記法中，將這些判斷提示實作為型別的值 <xref:Microsoft.Quantum.Math.Complex> 。
當預期的狀態可以數學計算時，這會很有説明。

### <a name="asserting-equality-of-quantum-operations"></a>判斷提示與量子作業是否相等 ###

到目前為止，我們都擔心要準備特定狀態的測試作業。
但通常，我們會對任意輸入（而不是單一固定輸入）的運作方式有興趣。
例如，假設我們已將 `U : ((Double, Qubit[]) => () : Adjoint)` 對應至單一單一運算子系列的作業，$U (t) $，並提供明確 `adjoint` 的區塊，而不是使用 `adjoint auto` 。
我們可能會想要判斷提示 $U ^ \dagger (t) = U (-t) $，如 $t $ 代表演進時間所預期。

大致上說，有兩個不同的策略可讓判斷提示指出這兩個作業 `U` ，並以相同的方式執行 `V` 。
首先，我們可以檢查 `U(target); (Adjoint V)(target);` 以指定的為基礎來保留每個狀態。
其次，我們可以檢查是否 `U(target); (Adjoint V)(target);` 有一半的纏結狀態會保留該纏結。
這些策略是由 canon 作業 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> 和分別執行 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> 。

> [!NOTE]
> 以上所討論的參考判斷提示會以 [choi 對於– Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)為基礎，這是一種數學架構，會將 $n $ 量子位上的作業與 $ 2n $ 纏結上的量子位狀態相關聯。
> 尤其是，$n $ 量子位上的身分識別作業會以纏結 state $ \ket{\ Beta_ {00} } \mathrel{： =} ( \ket {00} + \ket {11}) /\sqrt $ 的 $n $ 副本表示 {2} 。
> 作業 <xref:Microsoft.Quantum.Preparation.PrepareChoiState> 會執行這個 isomorphism，準備代表指定作業的狀態。

大致上，這些策略會以時間（空間折衷）來區分。
逐一查看每個輸入狀態需要額外的時間，而使用纏結作為參考需要儲存額外的量子位。
如果作業會執行可還原的傳統作業，讓我們只對計算基礎狀態的行為感興趣，則 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> 測試這組有限的輸入是否相等。

> [!TIP]
> 輸入狀態的反復專案是由列舉作業和所 <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> 處理 <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower> 。
> 這些作業對於將作業套用到兩個或多個集合之間的笛卡兒乘積的每個元素，更是很有用。

不過，這兩種方法會測試所檢查之作業的不同屬性。
因為就地判斷提示會多次呼叫每個作業，每個輸入狀態一次，任何隨機播放和測量結果可能會在呼叫之間變更。
相反地，參考的判斷提示會一次呼叫每個作業一次，因此它會檢查作業是否等於 *單一快照* 。
這兩項測試都有助於確保量副程式的正確性。


## <a name="further-reading"></a>深入閱讀 ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:Microsoft.Quantum.Diagnostics>
