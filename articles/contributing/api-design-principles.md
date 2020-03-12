---
title: '問 # API 設計原則'
description: '問 # API 設計原則'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: 03c32331f8988181ec6fedcfc207d752b4a880b2
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024197"
---
# <a name="q-api-design-principles"></a>問 # API 設計原則

## <a name="introduction"></a>簡介

問 # 是一種語言和平臺，可讓使用者撰寫、執行、瞭解及探索量子應用程式。
為了加強使用者的能力，當我們設計問 # 程式庫時，我們會遵循一組 API 設計原則來引導我們的設計，並協助我們為「量子開發」社區提供可用的程式庫。
本文將列出這些原則，並提供範例，以協助引導您在設計問 # Api 時如何套用它們。

> [!TIP]
> 這是相當詳細的檔，旨在協助引導媒體櫃開發和深入的程式庫投稿。
> 如果您是在 Q # 中撰寫自己的程式庫，或在[問 #](https://github.com/microsoft/QuantumLibraries)程式庫中提供較大的功能，您可能會發現它最有用。
>
> 另一方面，如果您想要瞭解如何更廣泛地參與「量子開發工具組」，建議您從「[貢獻指南](xref:microsoft.quantum.contributing)」開始。
> 如果您要尋找有關我們建議如何格式化問 # 程式碼的一般資訊，您可能會想要查看[樣式指南](xref:microsoft.quantum.contributing.style)。

## <a name="general-principles"></a>一般原則

**主要原則：** 公開將焦點放在量子應用程式的 Api。

- ✅**請**選擇反映演算法和應用程式之高階結構的作業和函式名稱。
- ⛔️**不**會公開主要著重于低層級執行詳細資料的 api。

**主要原則：** 使用範例使用案例來啟動每個 API 設計，以確保 Api 可直覺使用。

- ✅**確實**確保公用 API 的每個元件都有對應的使用案例，而不是嘗試針對從開頭進行的所有可能用法進行設計。
    以不同的方式進行，請不要引進公用 Api，以免其有用，但請確定 API 的每個部分都有*具體*的範例，其中會很有用。

  *範例：*
  - @"microsoft.quantum.canon.applytoeachca" 可用來做為 `ApplyToEachCA(H, _)`，以統一重迭狀態準備暫存器，這是許多配量演算法中的一般工作。 相同的作業也可以用於準備、數值和 oracle 型演算法中的許多其他工作。

- ✅**進行**靈感討論會和研討會新的 API 設計，以再次檢查它們是否直覺，並符合建議的使用案例。

  *範例：*
  - 檢查目前的 Q\# 程式碼，以瞭解新的 API 設計如何簡化並闡明現有的實作為。
  - 使用主要物件的代表來審查提議的 API 設計。

**主要原則：** 設計 Api 以支援和鼓勵可讀取的程式碼。

- ✅**確實**確保網域專家和非專家都能讀取程式碼。
- ✅**會將焦點**放在高階演算法中每個作業和函式的效果，並使用檔來深入瞭解適用的執行詳細資料。
- ✅**確實**遵循一般的[Q\# 樣式指南](xref:microsoft.quantum.contributing.style)（如果適用）。

**主要原則：** 將 Api 設計為穩定的，並提供向前相容性。

- ✅**在**需要中斷性變更時，可以正常地取代舊的 api。

- ✅ 提供「填充碼」作業和函式，**可讓現有**的使用者程式碼在淘汰期間正常運作。

  *範例：*
  - 將名為 `EstimateExpectation` 的作業重新命名為 `EstimateAverage`時，會引進名為 `EstimateExpectation` 的新作業，此作業會在其新名稱呼叫原始作業，讓現有的程式碼可以繼續正常運作。

- ✅**確實**使用 @"microsoft.quantum.core.deprecated" 屬性來與使用者通訊棄用功能。

- ✅ 重新命名作業或函式時 **，請**提供新的名稱做為 `@Deprecated`的字串輸入。

- ⛔️在預覽版本中，**請勿**移除至少六個月後的現有函式或作業，或至少兩年的支援版本。

## <a name="functions-and-operations"></a>函數和作業

**主要原則：** 確保每個函式和作業在 API 內都有一個定義完善的目的。

- ⛔️**不**會公開執行多個不相關工作的函式和作業。

**主要原則：** 盡可能將函式和作業設計為可重複使用，並預期未來的需求。

- ✅**執行**設計函式和作業，以便在相同的 API 和先前現有的程式庫中，妥善地與其他函式和作業一起撰寫。

  *範例：*
  - @"microsoft.quantum.canon.delay" 作業會對其輸入做出最低的假設，因此可以用來延遲在 Q # 標準程式庫或由使用者定義的任一作業的應用程式。
    <!-- TODO: define bad example. -->

- ✅**確實**會將純粹具決定性的傳統邏輯公開為函式，而不是作業。

  *範例：*
  - 會以決定性的方式寫入其浮點輸入的副程式，因此應該向使用者公開為 `Squared : Double -> Double`，而不是 `Square : Double => Double`作業。 這可讓您在多個位置呼叫副程式（例如：在其他函式中），並提供實用的優化資訊給編譯器，這可能會影響效能和優化。
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` 和 `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` 在保證方面有不同的確定性;兩者在不同的情況下都很有用。
  - 轉換量子作業之應用程式的 API 常式，通常會以決定性的方式執行，因此可做為 `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`之類的函式使用。

- ✅**會**視需要使用型別參數，將輸入型別一般化為每個函式和作業的合理程度。

  *範例：*
  - `ApplyToEach` 具有類型 `<'T>(('T => Unit), 'T[]) => Unit`，而不是其最常見應用程式的特定類型，`((Qubit => Unit), Qubit[]) => Unit`。

> [!TIP]
> 請務必預測未來的需求，但針對您的使用者解決具體的問題也很重要。
> 因此，基於此主要原則的作用，一律需要謹慎考慮並進行平衡，以避免開發 Api 「以防萬一」。

索引**鍵原則：** 選擇可預測的函式和作業的輸入和輸出類型，並傳達可以呼叫的目的。

- ✅**確實**會使用元組類型，以邏輯方式將輸入和輸出分組，而這些只會在同時被視為重要。 在這些情況下，請考慮使用使用者定義型別。

  *範例：*
  - 輸出另一個函式之本機 minima 的函式可能需要將搜尋間隔的界限當做輸入，因此 `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` 可能是適當的簽章。
  - 使用參數移位技術來估計機器學習分類器衍生的作業，可能需要同時採用移位和 unshifted 參數向量做為輸入。 在此情況下，類似于 `(unshifted : Double[], shifted : Double[])` 的輸入可能會很適當。

- ✅**會**在不同的函式和作業之間一致地排序輸入和輸出元組中的專案。

  *範例：*
  - 如果考慮兩個或函式或作業，其中每個都採用旋轉角度和目標 qubit 做為輸入，請確定在每個輸入元組中，都有相同的排序方式。 也就是，偏好 `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`，並 `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` 和 `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`。

**主要原則：** 設計函式和作業來與 Q\# 語言功能（例如部分應用程式）搭配運作。

- ✅**執行**輸入元組中的專案順序，使最常套用的輸入發生（也就是：讓部分應用程式的行為類似于 currying）。

  *範例：*
  - 使用浮點數和 qubit 做為輸入的作業 `ApplyRotation` 通常會先部分套用至浮點輸入，以搭配預期型別為 `Qubit => Unit`的輸入。 因此，`operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` 的簽章
      會與部分應用程式一致地搭配使用。
  - 一般而言，本指南表示將所有傳統資料放在輸入元組的所有 qubits 之前，但請使用良好的判斷，並檢查您的 API 在實務中的呼叫方式。

## <a name="user-defined-types"></a>使用者定義類型

**主要原則：** 使用使用者定義型別，協助讓 api 更具表達性且方便使用。

- ✅**會**引進新的使用者定義型別，為長和/或複雜型別提供有用的速記。

  *範例：*
  - 如果具有三個 qubit 陣列輸入的作業類型通常會做為輸入或當做輸出傳回，則會提供 UDT，例如 `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      有助於提供有用的速記。

- ✅**會**引進新的使用者定義型別，以指出給定的基底型別應該僅用於非常特殊的意義。

  *範例：*
  - 應該特別解讀為將傳統資料編碼成量子暫存器的作業，可能適用于具有使用者定義類型 `newtype InputEncoder = (Apply : (Qubit[] => Unit))`的標籤。

- ✅**確實**引進了新的使用者定義型別，其中包含允許未來擴充性的命名專案（例如：未來可能會包含其他命名專案的結果結構）。

  *範例：*
  - 當作業 `TrainModel` 公開大量的設定選項時，會將這些選項公開為新的 `TrainingOptions` UDT，並提供新的函式 `DefaultTrainingOptions : Unit -> TrainingOptions` 讓使用者能夠覆寫 TrainingOptions UDT 值中的特定已命名專案，同時仍然允許程式庫開發人員視需要加入新的 UDT 專案。

- ✅**請**在喜好設定中為新的使用者定義型別宣告命名專案，以要求使用者知道正確的元組解構。

  *範例：*
  - 當代表其極座標分解中的複數時，偏好 `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` 來 `newtype ComplexPolar = (Double, Double)`。

**主要原則：** 使用使用者定義型別，方法是減少認知負載，而不需要使用者學習其他概念和命名法。

- ⛔️**不**會引進使用者定義的型別，要求使用者經常使用解除包裝運算子（`!`），或通常需要多個解除包裝的層級。 可能的緩和策略包括：

  - 以單一專案公開使用者定義的型別時，請考慮定義該專案的名稱。 例如，請考慮 `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`的喜好設定。

  - 確保其他函數和作業可以直接接受「包裝的」 UDT 實例。

- ⛔️**不**會導入重複內建類型的新使用者定義類型，而不會提供其他表達。

  *範例：*
  - UDT `newtype QubitRegister = Qubit[]` 不會針對 `Qubit[]`提供任何額外的表達，因此更難使用，而不會有明顯的好處。
  - UDT `newtype LittleEndian = Qubit[]` 記載基礎暫存器的使用和解讀方式，進而提供其基底類型的其他表達。

- 除非絕對必要，否則⛔️**不**引進存取子函式;  在此情況下，強烈偏好命名專案。

  *範例：*
  - `newtype Complex = (Double, Double)`引進 UDT 時，建議您修改定義，以 `newtype Complex = (Real : Double, Imag : Double)` 介紹 `GetReal : Complex -> Double` 和 `GetImag : Complex -> Double`函數。

## <a name="namespaces-and-organization"></a>命名空間和組織

**主要原則：** 選擇可預測的命名空間名稱，並在每個命名空間中清楚地傳達函數、作業和使用者定義類型的用途。

- ✅**將命名空間命名為**`Publisher.Product.DomainArea`。

  *範例：*
  - 由 Microsoft 發佈的函式、作業和 Udt，屬於量子開發工具組的量子模擬功能，會放在 `Microsoft.Quantum.Simulation` 命名空間中。
  - `Microsoft.Quantum.Math` 代表 Microsoft 發佈的命名空間，做為與數學網域區域相關的量子開發工具組的一部分。

- ✅ 會將用於特定功能的作業、函式和使用者定義型別放入描述該功能的命名空間中，即使該功能是在不同的問題網域中使用也**是如此。**

  *範例：*
  - Microsoft 發佈的狀態準備 Api 會納入「量子開發工具組」中，並放在 `Microsoft.Quantum.Preparation`中。
  - Microsoft 在配量開發工具組中發佈的量子模擬 Api 會放入 `Microsoft.Quantum.Simulation`。

- ✅ 將只在特定網域內使用的作業、函式和使用者定義類型，**放入表示**其公用程式網域的命名空間。 如有需要，請使用子命名空間來指示每個網域特定命名空間中的焦點工作。

  *範例：*
  - Microsoft 所發佈的量子機器學習程式庫主要放在 @"microsoft.quantum.machinelearning" 命名空間中，但範例資料集是由 @"microsoft.quantum.machinelearning.datasets" 命名空間所提供。
  - Microsoft 在配量開發工具組中發佈的量子化學 Api 應該放入 `Microsoft.Quantum.Chemistry`。 執行約旦--Wigner 分解特有的功能可能會放在 `Microsoft.Quantum.Chemistry.JordanWigner`中，因此 [量子化學] 領域區域的主要介面不會與「處理」相關。

**主要原則：** 將命名空間和存取修飾詞一起使用，以刻意瞭解對使用者公開的 API 介面，並隱藏與 Api 的執行和測試相關的內部詳細資料。

- ✅ 在合理的情況下，請將執行 API 所需的所有函式和**作業放入**與所要執行的 api 相同的命名空間中，但以 "private" 或 "internal" 關鍵字標示，表示它們不是程式庫公用 api 介面的一部分。 使用以底線（`_`）開頭的名稱，以視覺化方式區分公用 callables 的私用和內部作業和函式。

  *範例：*
  - 作業名稱 `_Features` 表示對指定的命名空間和元件而言是私用的函式，而且應該伴隨 `internal` 關鍵字。

- ✅ 在罕見的情況下，需要一組豐富的私用函式或作業來執行給定命名空間的 API **，請**將它們放在新的命名空間中，以符合所要執行和結束于 `.Private`中的命名空間。

- ✅ 會將所有單元測試都**放入符合**受測命名空間的命名空間中，並以 `.Tests`結束。

## <a name="naming-conventions-and-vocabulary"></a>命名慣例和詞彙

**主要原則：** 在各種不同的物件上選擇清楚、可存取且可讀取的名稱和詞彙，包括量子新手和專家。

- ⛔️**不**會使用歧視性或 exclusionary 識別碼名稱，也不會有 API 檔批註的術語。

- ✅**確實**使用 API 檔批註來提供相關的內容、範例和參考，特別是針對更棘手的概念。

- ⛔️**不**會使用不必要難理解的識別碼名稱，或需要重要的量子演算法知識才能讀取。

  *範例：*
  - 偏好將「波幅放大反復專案」設為「Grover 反復專案」。

- ✅**確實**會選擇作業和函式名稱，以清楚地傳達所預期的可呼叫效果，而不是其執行方式。 請注意，執行可以和應該是

  *範例：*
  - 偏好「估計重迭」為「Hadamard 測試」，因為後者會傳達前者的實值。

- ✅**在**所有 Q\# api 之間以一致的方式使用單字：

  - **之外**

    - 判斷**提示：檢查**有關目的電腦及其 qubits 狀態的假設，可能是使用 unphysical 資源。 使用此動詞命令的作業應一律安全地卸載，而不會影響程式庫和可執行程式的功能。 請注意，與事實不同的是，判斷提示一般可能會依賴外部狀態，例如 qubit 暫存器的狀態、執行環境等等。 因為對外部狀態的相依性是一種副作用，所以判斷提示必須公開為作業，而不是函數。

    - **估計**：使用一或多個可能重複的測量，從測量結果估計傳統數量。

      *範例：*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **準備**：將配量作業或作業順序套用至一或多個假設以特定初始狀態啟動的 qubits （通常是 $ \ket{00\cdots 0} $），這會導致這些 qubits 的狀態演變成所需的結束狀態。 一般來說，在指定的啟動狀態以外的狀態下，**可能會**產生未定義的單一轉換，但仍**應**保留作業及其 adjoint 的「取消」並套用非 op。

      *範例：*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **量值**：將配量作業或作業順序套用至一或多個 qubits，並讀取傳統資料。

      *範例：*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Apply**：將配量作業或作業順序套用至一或多個 qubits，使這些 qubits 的狀態以一致的方式變更。 這個動詞是 Q\# 的命名法中最一般的動詞，**不應**在更特定的動詞更直接相關時使用。

  - **名詞**：

    - **事實**：僅取決於其輸入，而不是目的電腦的狀態、其環境或電腦 qubits 狀態的布林值條件。 相較于判斷提示，事實只對提供給該事實的*值*是敏感的。 例如：

      *範例：*
      - @"microsoft.quantum.diagnostics.equalityfacti"：代表兩個整數輸入的相等事實;提供做為輸入的整數會彼此相等，或不會與任何其他程式狀態無關。

    - **選項：** UDT，其中包含數個命名專案，可以做為函式或作業的「選擇性引數」。 例如：

      *範例：*
      - @"microsoft.quantum.machinelearning.trainingoptions" UDT 包含學習速率的命名專案、迷你批次大小，以及適用于 ML 訓練的其他可設定參數。

  - **形容詞**：

    - ⛔️ **New**：**不應**使用此形容詞，以避免在許多程式設計語言中將其使用方式與動詞（例如： C++、 C#、JAVA、TypeScript、PowerShell）混淆。

  - **介係詞：** 在某些情況下，介係詞可以用來進一步區分或澄清函數和作業名稱中名詞和動詞的角色。 不過，請務必謹慎且一致地採取此動作。

    - **As：** 表示函式的輸入和輸出代表相同的資訊，但輸出會將該資訊表示**為** *X* ，而不是其原始標記法。 這對於型別轉換函式而言特別常見。

      *範例：*
      - `IntAsDouble(2)` 表示輸入（`2`）和輸出（`2.0`）代表品質相同的資訊，但使用不同的 Q\# 資料類型來執行這項操作。

    - **來源：** 若要確保一致性，此介係詞**不應該**用來表示類型轉換函式，或任何其他**適合的情況**。

    - ⛔️**為：** **不應**使用此介係詞，因為它會與許多程式設計語言中的動詞一起使用，以避免混淆。
