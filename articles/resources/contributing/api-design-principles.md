---
title: '問 # API 設計原則'
description: '問 # API 設計原則'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: def6a9f12accfa399fd4db3783b9899fc743f025
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274550"
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

## <a name="general-principles"></a>一般準則

**主要原則：** 公開將焦點放在量子應用程式的 Api。

- ✅**選擇 [** 作業] 和 [函式名稱]，以反映演算法和應用程式的高階結構。
- ⛔️**不**會公開主要著重于低層級執行詳細資料的 api。

**主要原則：** 使用範例使用案例來啟動每個 API 設計，以確保 Api 可直覺使用。

- ✅**請確定公用**API 的每個元件都有對應的使用案例，而不是嘗試針對從開始進行的所有可能用法進行設計。
    以不同的方式進行，請不要引進公用 Api，以免其有用，但請確定 API 的每個部分都有*具體*的範例，其中會很有用。

  *範例：*
  - @"microsoft.quantum.canon.applytoeachca"可以用來以 `ApplyToEachCA(H, _)` 統一重迭狀態準備暫存器，這是許多配量演算法中的一般工作。 相同的作業也可以用於準備、數值和 oracle 型演算法中的許多其他工作。

- ✅**進行**集體討論和研討會新的 API 設計，再次檢查它們是否直覺，並符合建議的使用案例。

  *範例：*
  - 檢查目前 \# 的 Q 代碼，以瞭解新的 API 設計如何簡化並闡明現有的實作為。
  - 使用主要物件的代表來審查提議的 API 設計。

**主要原則：** 設計 Api 以支援和鼓勵可讀取的程式碼。

- ✅**請**確定網域專家和非專家都能讀取程式碼。
- ✅**請將焦點放在**高階演算法中每個作業和函式的效果，並使用檔深入探索適當的執行詳細資料。
- ✅**請盡可能遵循一般**的問與答[ \# 風格指南](xref:microsoft.quantum.contributing.style)。

**主要原則：** 將 Api 設計為穩定的，並提供向前相容性。

- ✅當需要中斷性變更時，**請**正常取代舊的 api。

- ✅**請**提供「填充碼」作業和函式，讓現有的使用者程式碼在淘汰期間能夠正確運作。

  *範例：*
  - 將名為的作業重新命名 `EstimateExpectation` 為時，會引進名為的新作業，此作業 `EstimateAverage` `EstimateExpectation` 會在其新名稱呼叫原始作業，讓現有的程式碼可以繼續正常運作。

- ✅**請**務必使用 @"microsoft.quantum.core.deprecated" 屬性，將棄用功能與使用者通訊。

- ✅重新命名作業或函式時，**請**提供新的名稱做為的字串輸入 `@Deprecated` 。

- ⛔️在預覽版本中，**請勿**移除至少六個月後的現有函式或作業，或至少兩年的支援版本。

## <a name="functions-and-operations"></a>函數和作業

**主要原則：** 確保每個函式和作業在 API 內都有一個定義完善的目的。

- ⛔️**不**會公開執行多個不相關工作的函式和作業。

**主要原則：** 盡可能將函式和作業設計為可重複使用，並預期未來的需求。

- ✅**執行**設計函式和作業，以便在相同的 API 和先前現有的程式庫中，與其他函式和作業共同撰寫。

  *範例：*
  - 作業 @"microsoft.quantum.canon.delay" 會對其輸入做出最低的假設，因此可以用來延遲在 Q # 標準程式庫或由使用者定義的任一作業的應用程式。
    <!-- TODO: define bad example. -->

- ✅**確實**會將純粹具決定性的傳統邏輯公開為函式，而不是作業。

  *範例：*
  - 會以決定性的方式寫入其浮點輸入的副程式，因此應該對使用者公開， `Squared : Double -> Double` 而不是做為作業 `Square : Double => Double` 。 這可讓您在多個位置呼叫副程式（例如：在其他函式中），並提供實用的優化資訊給編譯器，這可能會影響效能和優化。
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]`與 `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` 確定性方面的保證不同，這兩者在不同的情況下都很有用。
  - 轉換配量作業應用程式的 API 常式通常會以決定性的方式執行，因此可做為函式（例如）來使用 `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` 。

- ✅**請視**需要使用型別參數，將輸入型別一般化為每個函式和運算的合理程度。

  *範例：*
  - `ApplyToEach`具有類型 `<'T>(('T => Unit), 'T[]) => Unit` ，而不是其最常見應用程式的特定類型 `((Qubit => Unit), Qubit[]) => Unit` 。

> [!TIP]
> 請務必預測未來的需求，但針對您的使用者解決具體的問題也很重要。
> 因此，基於此主要原則的作用，一律需要謹慎考慮並進行平衡，以避免開發 Api 「以防萬一」。

索引**鍵原則：** 選擇可預測的函式和作業的輸入和輸出類型，並傳達可以呼叫的目的。

- ✅**請**使用元組類型，以邏輯方式將僅視為重要的輸入和輸出群組在一起。 在這些情況下，請考慮使用使用者定義型別。

  *範例：*
  - 輸出另一個函式之本機 minima 的函式可能需要將搜尋間隔的界限當做輸入，因此 `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` 可能是適當的簽章。
  - 使用參數移位技術來估計機器學習分類器衍生的作業，可能需要同時採用移位和 unshifted 參數向量做為輸入。 `(unshifted : Double[], shifted : Double[])`在此情況下，類似的輸入可能會很適當。

- ✅在不同的函式和作業之間一致地**執行**輸入和輸出元組中的專案順序。

  *範例：*
  - 如果考慮兩個或函式或作業，其中每個都採用旋轉角度和目標 qubit 做為輸入，請確定在每個輸入元組中，都有相同的排序方式。 也就是， `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` 偏好 `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 和 `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 。

**主要原則：** 設計函式和作業，使其適用于 Q \# 語言功能，例如部分應用程式。

- ✅**請**在輸入元組中執行排序專案，讓最常套用的輸入先發生（也就是：讓部分應用程式的行為類似 currying）。

  *範例：*
  - 使用 `ApplyRotation` 浮點數和 qubit 做為輸入的作業，通常會先與浮點輸入部分一起套用，以搭配預期輸入類型的運算使用 `Qubit => Unit` 。 因此，簽章`operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      會與部分應用程式一致地搭配使用。
  - 一般而言，本指南表示將所有傳統資料放在輸入元組的所有 qubits 之前，但請使用良好的判斷，並檢查您的 API 在實務中的呼叫方式。

## <a name="user-defined-types"></a>使用者定義類型

**主要原則：** 使用使用者定義型別，協助讓 api 更具表達性且方便使用。

- ✅**確實**引進了新的使用者定義型別，以提供有用的冗長和/或複雜型別的速記。

  *範例：*
  - 如果具有三個 qubit 陣列輸入的作業類型通常會當做輸入或作為輸出傳回，則會提供 UDT，例如`newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      有助於提供有用的速記。

- ✅**確實**會引進新的使用者定義型別，以指出給定的基底型別應該僅用於非常特殊的意義。

  *範例：*
  - 應該特別解讀為將傳統資料編碼成量子暫存器的作業，可能適用于具有使用者定義類型的標籤 `newtype InputEncoder = (Apply : (Qubit[] => Unit))` 。

- ✅**請**使用命名專案引進新的使用者定義型別，以允許未來的擴充性（例如：未來可能會包含其他命名專案的結果結構）。

  *範例：*
  - 當作業 `TrainModel` 公開大量設定選項時，將這些選項公開為新的 `TrainingOptions` UDT 並提供新的函式， `DefaultTrainingOptions : Unit -> TrainingOptions` 可讓使用者覆寫 TrainingOptions UDT 值中的特定已命名專案，同時仍然允許程式庫開發人員視需要加入新的 UDT 專案。

- ✅**請**在喜好設定中，為新的使用者定義類型宣告命名專案，以要求使用者知道正確的元組解構。

  *範例：*
  - 在其極座標分解中表示覆數時，偏好 `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` 使用 `newtype ComplexPolar = (Double, Double)` 。

**主要原則：** 使用使用者定義型別，方法是減少認知負載，而不需要使用者學習其他概念和命名法。

- ⛔️**不**會引進使用者定義的型別，要求使用者經常使用解除包裝運算子（ `!` ），或通常需要多個解除包裝的層級。 可能的緩和策略包括：

  - 以單一專案公開使用者定義的型別時，請考慮定義該專案的名稱。 例如，請考慮 `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` 將偏好設定為 `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` 。

  - 確保其他函數和作業可以直接接受「包裝的」 UDT 實例。

- ⛔️**不**會導入重複內建類型的新使用者定義類型，而不會提供其他表達。

  *範例：*
  - UDT `newtype QubitRegister = Qubit[]` 不提供任何額外的表達 `Qubit[]` ，因此很難使用，而且不會有明顯的好處。
  - UDT 會 `newtype LittleEndian = Qubit[]` 記錄基礎暫存器的使用和解讀方式，因此會提供其基底類型的其他表達。

- 除非絕對必要，否則⛔️**不**引進存取子函式;  在此情況下，強烈偏好命名專案。

  *範例：*
  - 引進 UDT 時，建議您將 `newtype Complex = (Double, Double)` 定義修改為， `newtype Complex = (Real : Double, Imag : Double)` 以引進函數 `GetReal : Complex -> Double` 和 `GetImag : Complex -> Double` 。

## <a name="namespaces-and-organization"></a>命名空間和組織

**主要原則：** 選擇可預測的命名空間名稱，並在每個命名空間中清楚地傳達函數、作業和使用者定義類型的用途。

- ✅將命名**空間命名為** `Publisher.Product.DomainArea` 。

  *範例：*
  - 由 Microsoft 發佈的函式、作業和 Udt，屬於量子開發工具組的量子模擬功能，會放在 `Microsoft.Quantum.Simulation` 命名空間中。
  - `Microsoft.Quantum.Math`代表 Microsoft 發佈的命名空間，做為與數學網域區域相關的量子開發工具組的一部分。

- ✅**將用於**特定功能的作業、函式和使用者定義類型，放在描述該功能的命名空間中，即使該功能是在不同的問題網域之間使用，也可以。

  *範例：*
  - Microsoft 發佈的狀態準備 Api 會放入，以作為「量子開發工具組」的一部分 `Microsoft.Quantum.Preparation` 。
  - Microsoft 在配量開發工具組中發佈的量子模擬 Api 會放入中 `Microsoft.Quantum.Simulation` 。

- ✅**請將僅**在特定網域內使用的作業、函式和使用者定義類型，放入表示其公用程式網域的命名空間。 如有需要，請使用子命名空間來指示每個網域特定命名空間中的焦點工作。

  *範例：*
  - Microsoft 所發佈的量子機器學習程式庫主要放在 @"microsoft.quantum.machinelearning" 命名空間中，但範例資料集是由 @"microsoft.quantum.machinelearning.datasets" 命名空間所提供。
  - 由 Microsoft 在配量開發工具組中發佈的量子化學 Api 應放入中 `Microsoft.Quantum.Chemistry` 。 執行約旦--Wigner 分解特有的功能可以放在中 `Microsoft.Quantum.Chemistry.JordanWigner` ，讓 [量子化學] 領域區域的主要介面不會與實作為顧慮。

**主要原則：** 將命名空間和存取修飾詞一起使用，以刻意瞭解對使用者公開的 API 介面，並隱藏與 Api 的執行和測試相關的內部詳細資料。

- ✅在合理的情況下，請將將 API 實作為所實作為 API 的相同命名空間，將所需的所有函式和作業**都放入**，但以 "private" 或 "internal" 關鍵字標示，表示它們不是程式庫公用 API 介面的一部分。 使用開頭為底線（）的名稱 `_` ，以視覺方式區分私用和內部作業和公用 callables 的函式。

  *範例：*
  - 作業名稱 `_Features` 會指出特定命名空間和元件的私用函式，而且應該伴隨 `internal` 關鍵字。

- ✅在很罕見的情況下，若要為指定的命名空間執行 API，請將**它們放在**符合所實和結尾之命名空間的新命名空間中 `.Private` 。

- ✅**將所有**單元測試都放入符合受測命名空間的命名空間中，並以結尾 `.Tests` 。

## <a name="naming-conventions-and-vocabulary"></a>命名慣例和詞彙

**主要原則：** 在各種不同的物件上選擇清楚、可存取且可讀取的名稱和詞彙，包括量子新手和專家。

- ⛔️**不**會使用歧視性或 exclusionary 識別碼名稱，也不會有 API 檔批註的術語。

- ✅**請務必使用 API**檔批註來提供相關的內容、範例和參考，特別是針對更棘手的概念。

- ⛔️**不**會使用不必要難理解的識別碼名稱，或需要重要的量子演算法知識才能讀取。

  *範例：*
  - 偏好將「波幅放大反復專案」設為「Grover 反復專案」。

- ✅**請**選擇作業和函式名稱，以清楚地傳達所需的可呼叫效果，而不是其實作為。 請注意，您可以在[API 檔批註](xref:microsoft.quantum.guide.filestructure#documentation-comments)中記載和執行。

  *範例：*
  - 偏好「估計重迭」為「Hadamard 測試」，因為後者會傳達前者的實值。

- ✅在所有 Q api 中，以一致的**方式使用單字** \# ：

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

    - **Apply**：將配量作業或作業順序套用至一或多個 qubits，使這些 qubits 的狀態以一致的方式變更。 這個動詞是 Q 命名法中最常見的動詞 \# ，**不應**在更特定的動詞更直接相關時使用。

  - **名詞**：

    - **事實**：僅取決於其輸入，而不是目的電腦的狀態、其環境或電腦 qubits 狀態的布林值條件。 相較于判斷提示，事實只對提供給該事實的*值*是敏感的。 例如：

      *範例：*
      - @"microsoft.quantum.diagnostics.equalityfacti"：表示兩個整數輸入的相等事實;提供做為輸入的整數會彼此相等，或不會與任何其他程式狀態無關。

    - **選項：** UDT，其中包含數個命名專案，可以做為函式或作業的「選擇性引數」。 例如：

      *範例：*
      - @"microsoft.quantum.machinelearning.trainingoptions"UDT 包含學習速率的命名專案、迷你批次大小，以及適用于 ML 訓練的其他可設定參數。

  - **形容詞**：

    - ⛔️ **New**：**不應**使用此形容詞，以避免在許多程式設計語言中將其使用方式與動詞（例如： c + +、c #、JAVA、TypeScript、PowerShell）混淆。

  - **介係詞：** 在某些情況下，介係詞可以用來進一步區分或澄清函數和作業名稱中名詞和動詞的角色。 不過，請務必謹慎且一致地採取此動作。

    - **As：** 表示函式的輸入和輸出代表相同的資訊，但輸出會將該資訊表示**為** *X* ，而不是其原始標記法。 這對於型別轉換函式而言特別常見。

      *範例：*
      - `IntAsDouble(2)`表示輸入（ `2` ）和輸出（ `2.0` ）都代表品質相同的資訊，但使用不同的 Q \# 資料類型來執行這項操作。

    - **來源：** 若要確保一致性，此介係詞**不應該**用來表示類型轉換函式，或任何其他**適合的情況**。

    - ⛔️**為：** **不應**使用此介係詞，因為它會與許多程式設計語言中的動詞一起使用，以避免混淆。
