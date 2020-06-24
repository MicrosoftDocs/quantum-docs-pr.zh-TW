---
title: 'Q # 標準程式庫中的診斷'
description: '瞭解用於在量副程式中攔截錯誤或錯誤的 Q # 標準程式庫中的診斷功能和作業。'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: fa5173f710dd9e0b0b2c110e45aa0bf019111aca
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274607"
---
# <a name="diagnostics"></a>診斷 #

與傳統開發一樣，要能夠診斷量副程式中的錯誤和錯誤是很重要的。
問 # 標準程式庫提供各種不同的方式來確保量副程式的正確性，如中所述 <xref:microsoft.quantum.guide.testingdebugging> 。
大致上來說，這項支援是以函式和作業的形式提供，以指示目的電腦向主機程式或開發人員提供額外的診斷資訊，或是強制執行由函數或作業呼叫所表示的條件和非變異性的正確性。

## <a name="machine-diagnostics"></a>機器診斷 ##

您可以使用函 <xref:microsoft.quantum.intrinsic.message> 式，以電腦相依的方式來記錄訊息，以取得有關傳統值的診斷。
根據預設，這會將字串寫入主控台。
與字串插值一起使用， <xref:microsoft.quantum.intrinsic.message> 可讓您輕鬆地報告有關傳統值的診斷資訊：

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message`具有簽章 `(String -> Unit)` ，再次表示無法從 Q # 中觀察發出的偵錯工具記錄訊息。

<xref:microsoft.quantum.diagnostics.dumpmachine>和 <xref:microsoft.quantum.diagnostics.dumpregister> callables 會指示目的電腦提供有關目前已配置之所有 qubits 的診斷資訊，或分別針對特定的 qubits 註冊。
每一部目的電腦都會因回應傾印指令所提供的診斷資訊而有所不同。
例如，[完整狀態](xref:microsoft.quantum.machines.full-state-simulator)模擬器目的機器會提供主機程式，其狀態向量會在內部用來代表 qubits 的暫存器。
相較之下， [Toffoli](xref:microsoft.quantum.machines.toffoli-simulator)模擬器目的電腦會針對每個 qubit 提供單一的傳統位。

 若要深入瞭解[完整狀態模擬器的](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` 輸出，請參閱[測試和調試](xref:microsoft.quantum.guide.testingdebugging#dump-functions)程式一文的傾印函式一節。


## <a name="facts-and-assertions"></a>事實和判斷提示 ##

如[測試和](xref:microsoft.quantum.guide.testingdebugging)偵測中所述，簽章或的函式或作業會 `Unit -> Unit` `Unit => Unit` 分別標記為*單元測試*。
每個單元測試通常包含一個小型的配量程式，以及一個或多個檢查該程式正確性的條件。
這些條件可以是_事實_的形式，它會檢查輸入的值，或_判斷_提示，檢查傳遞做為輸入的一個或多個 qubits 的狀態。

例如， `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` 代表 $1 + 1 = $2 的數學事實，而則 `AssertQubit(One, qubit)` 表示測量 `qubit` 會傳回 `One` 具有確定性的條件。
在先前的案例中，我們可以檢查只指定其值的條件是否正確，而在後者中，我們必須知道 qubit 狀態的相關資訊，才能評估判斷提示。

Q # 標準程式庫提供數個不同的函數來表示事實，包括：

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>測試 Qubit 狀態 ###

實際上，判斷提示會依賴傳統的量子機制模擬不需要遵守[無複製定理](https://arxiv.org/abs/quant-ph/9607018)的事實，因此我們可以在針對目的電腦使用模擬器時，做出 unphysical 測量和判斷提示。
因此，我們可以先在傳統模擬器上測試個別作業，再于硬體上進行部署。
在不允許評估判斷提示的目的電腦上， <xref:microsoft.quantum.intrinsic.assert> 可以放心忽略的呼叫。

更常見的情況是，作業判斷提示 <xref:microsoft.quantum.intrinsic.assert> 在給定的 Pauli 基礎測量指定的 qubits 時，一定會有指定的結果。
如果判斷提示失敗，則會以指定的訊息呼叫來結束執行 `fail` 。
根據預設，不會執行這項作業;可支援的模擬器應該提供執行執行時間檢查的執行。
`Assert`具有簽章 `((Pauli[], Qubit[], Result, String) -> ())` 。
由於 `Assert` 是具有空的元組做為其輸出類型的函式，因此在 `Assert` Q # 程式中不會有任何來自呼叫的效果可觀察。

在 <xref:microsoft.quantum.intrinsic.assertprob> 給定的 Pauli 基礎中測量給定 qubits 的運算函式，會在某些容錯範圍內具有給定機率的指定結果。
容錯為加法（例如 `abs(expected-actual) < tol` ）。
如果判斷提示失敗，則會以指定的訊息呼叫來結束執行 `fail` 。
根據預設，不會執行這項作業;可支援的模擬器應該提供執行執行時間檢查的執行。
`AssertProb`具有簽章 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` 。 第一個 `Double` 參數會提供所需的結果機率，第二個則是容錯。

我們可以執行高於單一測量的宣告，使用模擬器用來代表 qubit 內部狀態的傳統資訊適合複製，因此我們不需要實際執行測量來測試判斷提示。
特別是，這可讓我們瞭解在實際硬體上可能無法進行的*不相容*測量。

假設這 `P : Qubit => Unit` 是一項作業，可在其輸入為 state $ \ket $ 時準備狀態 $ \ket{\psi} $ {0} 。
讓 $ \ket{\psi '} $ 成為所備妥的實際狀態 `P` 。
然後，只有在 $ \ket{\psi} $ 所描述的軸中測量 $ \ket{\psi '} $ 一律傳回時，$ \ket{\psi} = \ket{\psi '} $ 才會傳回 `Zero` 。
也就是說，只有在} \braket{\psi | \psi '} = 1 時，\begin{align} \ket{\psi} = \ket{\psi '} 才會 \text{。
\end{align} 使用序言中定義的基本作業，我們可以直接執行測量值，以在 `Zero` $ \ket{\psi} $ 是其中一個 Pauli 運算子的 eigenstate 時傳回。


當 <xref:microsoft.quantum.diagnostics.assertqubit> 我們想要測試判斷提示 $ \ket{\psi} = \ket $ 時，作業會提供特別有用的縮寫來進行此操作 {0} 。
例如，當我們在釋放 ancilla qubits 至 $ \ket $ 之前，uncomputed 會將 {0} 其傳回。
{0}當我們想要判斷提示兩個狀態準備 `P` 和 `Q` 作業都準備相同的狀態，以及支援時，對 $ \ket $ 進行判斷提示也很有用 `Q` `Adjoint` 。
特別是，

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

不過，更常見的情況是，我們可能無法存取與 Pauli 運算子 eigenstates 不一致的狀態判斷提示。
例如，$ \ket{\psi} = （\ket {0} + e ^ {i \pi/8} \ket {1} ）/\sqrt {2} $ 不是任何 eigenstate 運算子的 Pauli，因此我們無法使用 <xref:microsoft.quantum.intrinsic.assertprob> 來唯一判斷 state $ \ket{\psi '} $ 等於 $ \ket{\psi} $。
相反地，我們必須將判斷提示 $ \ket{\psi '} = \ket{\psi} $ 分解成可使用模擬器支援的原始物件直接測試的假設。
若要這麼做，請將 $ \ket{\psi} = \Alpha \ket {0} + \Beta \ket {1} $ 用於複數 $ \Alpha = \_ r + a \_ i $ 和 $ \Beta $。
請注意，此運算式需要四個實數 $ \{ a \_ r、a \_ i、b \_ r、b \_ i \} $ 來指定，因為每個複數都可以表示為實數和虛數部分的總和。
不過，由於全域階段，我們可以選擇 $a \_ i = $0，因此我們只需要三個實數來唯一指定單一 qubit 狀態。

因此，我們需要指定三個彼此獨立的判斷提示，以便判斷提示所預期的狀態。
我們會藉由找 `Zero` 出每個 Pauli 測量的機率，以提供 $ \Alpha $ 和 $ \Beta $，並個別進行判斷提示。
讓 $x $、$y $ 和 $z $ 分別是 `Result` Pauli $X $、$Y $ 和 $Z $ 度量的值。
然後，使用量測的可能性函式，\begin{align} \Pr （x = \texttt{Zero} | \Alpha，\Beta） & = \frac12 + a \_ r b \_ r + a \_ i b \_ i \\ \\ \Pr （y = \texttt{Zero} | \Alpha，\Beta） & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \Pr （z = \texttt{Zero} | \Alpha，\Beta） & = \frac12\left （1 + a \_ r ^ 2 + a \_ i ^ 2 + b \_ r ^ 2 + b \_ i ^ 2 \right）。
\end{align}

作業會 <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 以類型的值，將指定的 $ \Alpha $ 和 $ \Beta $ 標記法實作為這些判斷提示 <xref:microsoft.quantum.math.complex> 。
當預期的狀態可以數學計算時，這會很有説明。

### <a name="asserting-equality-of-quantum-operations"></a>判斷量子作業是否相等 ###

到目前為止，我們都擔心要準備特定狀態的測試作業。
不過，通常我們會對任意輸入（而不是單一固定輸入）的操作方式感興趣。
例如，假設我們已實作為 `U : ((Double, Qubit[]) => () : Adjoint)` 一個對應于一系列單一運算子 $U （t） $ 的作業，並提供明確的 `adjoint` 區塊，而不是使用 `adjoint auto` 。
如果 $t $ 代表進化時間，我們可能會想要判斷提示 $U ^ \dagger （t） = U （-t） $ （如預期）。

大致來說，我們可以遵循兩個不同的策略，讓判斷提示中的兩個作業 `U` 和 `V` 動作都相同。
首先，我們可以檢查 `U(target); (Adjoint V)(target);` 以指定的方式來保留每個狀態。
第二，我們可以檢查，以 `U(target); (Adjoint V)(target);` 光子狀態的一半來保留該會任何牽連。
這些策略是由 canon 作業 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> 和分別執行 <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced> 。

> [!NOTE]
> 上述所討論的參考判斷提示適用于[Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)，這是一種數學架構，其會將 $n $ qubits 上的作業與 $ 2n $ 光子上的 qubits 狀態相關聯。
> 特別是，$n $ qubits 上的身分識別作業是由光子 state $ \ket{\ Beta_ {00} } \mathrel{： =} （\ket {00} + \ket {11} ）/\sqrt $ 的 $n $ 複本所表示 {2} 。
> 作業 <xref:microsoft.quantum.preparation.preparechoistate> 會執行此 isomorphism，並準備代表給定作業的狀態。

大致上，這些策略會以時間-空間取捨來區分。
逐一查看每個輸入狀態需要額外的時間，而使用會任何牽連做為參考時，需要儲存額外的 qubits。
在作業執行可復原的傳統作業的情況下，我們只會對其運算基礎狀態的行為感興趣， <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> 測試此限制的輸入集合是否相等。

> [!TIP]
> 輸入狀態的反復專案是由列舉作業和處理 <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> <xref:microsoft.quantum.canon.iteratethroughcartesianpower> 。
> 在兩個或多個集合之間將作業套用至笛卡兒產品的每個元素時，這些作業會更有用。

不過，這兩種方法會對受測作業的不同屬性進行測試。
由於就地判斷提示會多次呼叫每個作業，因此針對每個輸入狀態，任何隨機的選擇和測量結果可能會在呼叫之間變更。
相較之下，參考的判斷提示只會呼叫每個作業一次，因此它會檢查*單一快照中*的作業是否相等。
這兩個測試都有助於確保量副程式的正確性。


## <a name="further-reading"></a>深入閱讀 ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:microsoft.quantum.diagnostics>
