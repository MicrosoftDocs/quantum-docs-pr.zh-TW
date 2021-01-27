---
title: Q# API 設計原則
description: Q# API 設計原則
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.api-design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 452b32141dc660acbe8ef28530f1430e5acff9aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856693"
---
# <a name="no-locq-api-design-principles"></a>Q# API 設計原則

## <a name="introduction"></a>簡介

作為一種語言和平臺，讓 Q# 使用者能夠撰寫、執行、瞭解和探索量子應用程式。
為了讓使用者能夠使用，當我們設計 Q# 程式庫時，我們會遵循一組 API 設計原則來引導我們的設計，並協助我們為量子開發社區提供可用的程式庫。
本文將列出這些原則，並提供範例來說明如何在設計 api 時套用這些原則 Q# 。

> [!TIP]
> 這是一份相當詳細的檔，旨在協助引導程式庫開發和深度程式庫投稿。
> 如果您要在中撰寫自己的程式庫，或在程式庫存放庫中提供 Q# 較大的功能，您[ Q# ](https://github.com/microsoft/QuantumLibraries)可能會發現它最有用。
>
> 相反地，如果您想要瞭解如何更普遍地參與量子開發工具組，我們建議您從 [貢獻指南](xref:microsoft.quantum.contributing)開始。
> 如果您要尋找更多有關如何建議您格式化程式碼的一般資訊 Q# ，您可能會想要查看 [樣式指南](xref:microsoft.quantum.contributing.style)。

## <a name="general-principles"></a>一般準則

**主要原則：** 公開將焦點放在量子應用程式上的 Api。

- ✅**請** 選擇可反映演算法和應用程式高層級結構的作業和函式名稱。
- ⛔️ **不** 會公開焦點主要在低層級的執行詳細資料上的 api。

**主要原則：** 使用範例使用案例來開始每個 API 設計，以確保 Api 可直覺化。

- ✅**確定公用** API 的每個元件都有相對應的使用案例，而不是嘗試針對所有可能的使用方式進行設計。
    以不同的方式放置，如果公用 Api 很有用，請不要引進公用 Api，但請確定 API 的每個部分都有 *具體* 的範例，其中將會很有用。

  *範例：*
  - @"microsoft.quantum.canon.applytoeachca" 可以用 `ApplyToEachCA(H, _)` 來準備在統一迭加狀態中的暫存器，也就是許多量子演算法中常見的工作。 相同的作業也可以用於準備、數值和 oracle 演算法的許多其他工作。

- ✅**進行** 集體討論並研討會新的 API 設計，以再次檢查它們是否直覺，並符合建議的使用案例。

  *範例：*
  - 檢查目前的 Q 程式 \# 代碼，以瞭解新的 API 設計如何簡化和闡明現有的實作為。
  - 使用主要物件的代表來審核提議的 API 設計。

**主要原則：** 設計 Api 來支援和鼓勵可讀取的程式碼。

- ✅**請** 確定網域專家和非專家都可讀取程式碼。
- ✅**請將焦點** 放在高階演算法內的每個作業和功能的效果，並使用檔以適當的方式深入探索執行詳細資料。
- ✅**請遵循常見** 的 [Q \# 樣式指南](xref:microsoft.quantum.contributing.style)（如果適用）。

**主要原則：** 將 Api 設計為穩定，並提供向前相容性。

- ✅需要中斷變更時， **請確實** 取代舊的 api。

- ✅**請** 提供「填充碼」作業和函式，以允許現有使用者程式碼在淘汰期間正常運作。

  *範例：*
  - 將呼叫的作業重新命名時 `EstimateExpectation`   `EstimateAverage` ，會引入名為的新作業，該作業會   `EstimateExpectation` 以新名稱呼叫原始作業，讓現有的程式碼可以繼續正常運作。

- ✅**請** 使用 @"microsoft.quantum.core.deprecated" 屬性將棄用功能傳達給使用者。

- ✅ 重新命名作業或函式時，請提供新的名稱 **做** 為的字串輸入 `@Deprecated` 。

- ⛔️ **不** 會移除現有的函式或作業，但在預覽版本中，至少有六個月的淘汰期，或至少兩年的支援版本。

## <a name="functions-and-operations"></a>函數和作業

**主要原則：** 確定每個函式和作業在 API 內都有一個定義完善的用途。

- ⛔️ **不** 會公開執行多個不相關工作的函式和作業。

**主要原則：** 盡可能將函式和作業設計為可重複使用，並預測未來的需要。

- ✅請在相同的 API 和先前現有的程式庫中， **進行** 設計功能和作業，以與其他函式和作業一起撰寫。

  *範例：*
  - 作業 @"microsoft.quantum.canon.delay" 會對其輸入進行最基本的假設，因此可用來延遲在 Q# 標準程式庫中或由使用者定義之任何作業的應用程式。
    <!-- TODO: define bad example. -->

- ✅會公開純決定性的傳統邏輯作為函式， **而不是** 作業。

  *範例：*
  - 以決定性方式寫入其浮點數輸入的副程式可依決定性寫入，因此應該向使用者公開， `Squared : Double -> Double` 而不是做為作業 `Square : Double => Double` 。 這可讓您在多個位置呼叫副程式 (例如：) 的其他函式內，並提供實用的優化資訊給編譯器，可能會影響效能和優化。
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` 和 `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` 確定性方面的保證不同，兩者在不同的情況下都很有用。
  - 轉換量子作業應用程式的 API 常式通常可以用決定性的方式來執行，因此可以用像這樣的功能   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` 。

- ✅**請視** 需要使用型別參數，將輸入類型一般化為每個函式和作業的合理程度。

  *範例：*
  - `ApplyToEach` 具有類型 `<'T>(('T => Unit), 'T[]) => Unit` ，而不是其最常見的應用程式的特定類型 `((Qubit => Unit), Qubit[]) => Unit` 。

> [!TIP]
> 請務必預測未來的需求，但為您的使用者解決具體問題也很重要。
> 因此，請務必謹慎考慮並進行平衡，以避免開發 Api 「單純的情況」。

**主要原則：** 選擇可預測的函式和作業的輸入和輸出類型，並傳達可呼叫的目的。

- ✅**請** 使用元組類型，以邏輯方式將只視為重要的輸入和輸出群組在一起。 在這些情況下，請考慮使用使用者定義型別。

  *範例：*
  - 輸出另一個函式之本機最小值的函式可能需要以搜尋間隔作為輸入的界限，因此 `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` 可能是適當的簽章。
  - 使用參數移位技術來評估機器學習分類器衍生的作業，可能需要同時採用移位和 unshifted 參數向量做為輸入。 `(unshifted : Double[], shifted : Double[])`在此情況下，類似的輸入可能會很適合。

- ✅將輸入和輸出元集中的 **專案順序一致** 地跨不同的函式和作業。

  *範例：*
  - 如果考慮到兩個或各自採用旋轉角度和目標量子位做為輸入的兩個 or 函數或作業，請確定其在每個輸入元組中的排序方式都相同。 也就是， `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` 偏好 `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 和 `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 。

**主要原則：** 設計函數和作業，以便與 \# 部分應用程式等 Q 語言功能搭配運作。

- ✅在輸入元組中執行順序專案，讓最常套用的輸入先 (**也** 就是：，讓部分應用程式的運作方式類似于 currying) 。

  *範例：*
  - 以 `ApplyRotation` 浮點數和量子位作為輸入的作業，通常會先部分套用浮點數輸入，以便與預期類型輸入的作業搭配使用 `Qubit => Unit` 。 因此，簽章 `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      在部分應用程式中最一致的運作方式。
  - 一般而言，本指引表示在輸入元組中的所有量子位之前，將所有傳統資料放在一起，但請使用良好的判斷，並檢查您的 API 在實務上的呼叫方式。

## <a name="user-defined-types"></a>使用者定義類型

**主要原則：** 使用使用者定義型別有助於讓 api 更具表達性且方便使用。

- ✅**請** 加入新的使用者定義型別，以提供適用于 long 和/或複雜類型的實用速記。

  *範例：*
  - 在具有三個量子位陣列輸入的作業類型時，通常會將其視為輸入或傳回做為輸出，並提供如下的 UDT： `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      有助於提供實用的速記。

- ✅**請** 建立新的使用者定義型別，以指出指定的基底類型應該只用于非常特殊的意義。

  *範例：*
  - 應特別解讀為將傳統資料編碼成量子暫存器的作業，可能適合以使用者定義型別來標記 `newtype InputEncoder = (Apply : (Qubit[] => Unit))` 。

- ✅**請** 利用命名專案來引進新的使用者定義型別，以允許未來的擴充性 (例如：可能會在未來的) 中包含其他已命名專案的結果結構。

  *範例：*
  - 當作業 `TrainModel` 公開大量的設定選項時，以新的 udt 公開這些選項，   `TrainingOptions` 並提供新的函式，   `DefaultTrainingOptions : Unit -> TrainingOptions` 可讓使用者在 TrainingOptions UDT 值中覆寫特定的已命名專案，同時仍然允許程式庫開發人員適當地加入新的 UDT 專案。

- ✅**請** 依照喜好設定為新的使用者定義類型宣告命名專案，要求使用者知道正確的元組解構。

  *範例：*
  - 在其極值分解中表示覆數時，偏好   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` 使用   `newtype ComplexPolar = (Double, Double)` 。

**主要原則：** 使用使用者定義型別的方式可減少認知負載，而且不需要使用者學習其他概念和術語。

- ⛔️ **不** 會引進使用者定義型別，而使用者定義型別需要使用者經常使用解除包裝運算子 (`!`) ，或者通常需要多個解除包裝的層級。 可能的緩和策略包括：

  - 以單一專案公開使用者定義型別時，請考慮定義該專案的名稱。 例如，請考慮 `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` 到的喜好設定 `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` 。

  - 確保其他函式和作業可以直接接受「包裝」的 UDT 實例。

- ⛔️ **不** 會引進新的使用者定義型別，這些類型會複製內建類型，而不會提供其他表達。

  *範例：*
  - UDT `newtype QubitRegister = Qubit[]` 不提供任何其他表達 `Qubit[]` ，因此不會有明顯的優點，因此難以使用。
  - UDT 會記載 `newtype LittleEndian = Qubit[]` 如何使用和解讀基礎暫存器，進而提供其基底類型的其他表達。

- 除非絕對必要，否則⛔️ **不** 會引進存取子函數;  在此情況下，強烈偏好命名專案。

  *範例：*
  - 引入 UDT 時 `newtype Complex = (Double, Double)` ，偏好將定義修改為，   `newtype Complex = (Real : Double, Imag : Double)` 以引入函式 `GetReal : Complex -> Double` 和   `GetImag : Complex -> Double` 。

## <a name="namespaces-and-organization"></a>命名空間和組織

**主要原則：** 選擇可預測的命名空間名稱，並清楚地傳達每個命名空間中的函式、作業和使用者定義類型的用途。

- ✅將命名 **空間命名為** `Publisher.Product.DomainArea` 。

  *範例：*
  - 由 Microsoft 發佈的函式、作業和 Udt 是量子開發工具組之量子模擬功能的一部分，會放在   `Microsoft.Quantum.Simulation` 命名空間中。
  - `Microsoft.Quantum.Math` 代表 Microsoft 在與數學網域區域相關的量子開發工具組中所發佈的命名空間。

- ✅**請將用於** 特定功能的作業、函式和使用者定義類型，放入描述該功能的命名空間中，即使是在不同的問題網域中使用該功能。

  *範例：*
  - 由 Microsoft 發佈作為量子開發工具組一部分的狀態準備 Api 將會放入   `Microsoft.Quantum.Preparation` 。
  - Microsoft 在量子開發工具組中發佈的量子模擬 Api 將會放入   `Microsoft.Quantum.Simulation` 。

- ✅**將作業**、函式和使用者定義型別只用于特定網域中，以表示其公用程式網域。 如有需要，請使用子命名空間來指出每個特定領域命名空間內的焦點工作。

  *範例：*
  - Microsoft 所發行的量子機器學習程式庫主要放在 @"microsoft.quantum.machinelearning" 命名空間中，但範例資料集是由 @"microsoft.quantum.machinelearning.datasets"   命名空間提供。
  - 由 Microsoft 發佈作為量子開發工具組一部分的量子化學 Api 應該放入 `Microsoft.Quantum.Chemistry` 。 執行約旦--Wigner 分解的特定功能可能會放入 `Microsoft.Quantum.Chemistry.JordanWigner` ，因此量子化學網域區域的主要介面並不在意實行。

**主要原則：** 使用命名空間和存取修飾詞，以刻意刻意瞭解對使用者公開的 API 介面，以及隱藏與 Api 的執行和測試相關的內部詳細資料。

- ✅ 如果 **合理，請將將 api** 實作為所要執行之 api 的相同命名空間中的所有函式和作業放在同一命名空間中，但標示為「私用」或「內部」關鍵字，表示它們不是程式庫公用 API 介面的一部分。 使用以底線 (開頭的名稱 `_`) ，以視覺化方式區分私用和內部作業以及公用 callables 的函式。

  *範例：*
  - 作業名稱 `_Features` 表示對指定的命名空間和元件而言是私用的函式，且應伴隨 `internal` 關鍵字。

- ✅ 在罕見的情況下，需要一組廣泛的私用函式或作業以針對指定的命名 **空間執行 API 時，請** 將它們放在符合所要執行和結束之命名空間的新命名空間中 `.Private` 。

- ✅**請** 將所有單元測試放入符合受測命名空間的命名空間中，並在結尾 `.Tests` 。

## <a name="naming-conventions-and-vocabulary"></a>命名慣例和詞彙

**主要原則：** 選擇在各種不同的物件範圍內清楚、可存取且可讀取的名稱和術語，包括量子新手和專家。

- ⛔️ **不** 使用歧視性或排他性行為識別碼名稱，也不使用 API 檔批註中的術語。

- ✅**請使用 API** 檔批註來提供相關的內容、範例和參考，特別是針對更困難的概念。

- ⛔️ **不要** 使用不必要難理解的識別碼名稱，或需要大量量子演算法知識才能讀取的識別碼名稱。

  *範例：*
  - 偏好「幅度放大反覆運算」至「格羅弗反復專案」。

- ✅**請** 選擇作業和函式名稱，以明確地傳達可呼叫的預期效果，而不是其實作為。 請注意，您可以和應該記載在 [API 檔批註](xref:microsoft.quantum.qsharp.comments#documentation-comments)中的執行。

  *範例：*
  - 將「估計重迭」視為「Hadamard 測試」，因為後者會傳達前者的執行方式。

- ✅**請** 在所有 Q api 中以一致的方式使用單字 \# ：

  - **動詞：**

    - 判斷 **提示：檢查** 目的電腦及其量子位狀態的相關假設是否保留，可能是使用 unphysical 資源。 使用這個動詞命令的作業應該一律安全地移除，而不會影響程式庫和可執行程式的功能。 請注意，不同于事實，判斷提示通常會取決於外部狀態，例如量子位暫存器的狀態、執行環境等等。 因為外部狀態的相依性是一種副作用，所以判斷提示必須公開為作業，而不是函數。

    - **估計**：使用一或多個可能重複的度量，從測量結果中估計傳統數量。

      *範例：*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **準備**：將量子作業或作業順序套用至一或多個量子位，假設要在特定初始狀態下啟動 (通常是 $ \ket{00\cdots 0} $) ，導致這些量子位的狀態演進至所需的結束狀態。 一般情況下，對指定啟動狀態以外的狀態採取動作， **可能會** 導致未定義的單一轉換，但是仍 **應** 保留作業及其 adjoint 「取消」並套用「無作業」。

      *範例：*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Measure**：將量子作業或作業順序套用至一或多個量子位，然後再讀取傳統資料。

      *範例：*
      - @"Microsoft.Quantum.Intrinsic.Measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Apply**：將量子作業或作業順序套用至一或多個量子位，使這些量子位的狀態變更為一致的方式。 此動詞命令是 Q 命名法中最常見的動詞命令 \# ， **不應** 在更明確相關的動詞時使用。

  - **名詞**：

    - **事實**：只取決於其輸入的布林條件，而不是目的電腦的狀態、其環境或電腦量子位的狀態。 相較于判斷提示，事實只會對提供給該事實的 *值* 有所區分。 例如：

      *範例：*
      - @"microsoft.quantum.diagnostics.equalityfacti"：表示兩個整數輸入的相等事實;提供做為輸入的整數會彼此相等，或與任何其他程式狀態無關。

    - **選項：** 包含數個命名專案的 UDT，這些專案可作為函式或作業的「選擇性引數」。 例如：

      *範例：*
      - @"microsoft.quantum.machinelearning.trainingoptions"UDT 包含適用于學習速率、迷你批次大小和其他可設定之 ML 訓練參數的命名專案。

  - **形容詞**：

    - ⛔️ **New**： **不應** 使用這項形容詞，以避免在許多程式設計語言中將其使用方式與動詞混淆 (例如： c + +、c #、JAVA、TypeScript、PowerShell) 。

  - **介係詞：** 在某些情況下，介係詞可用來進一步區分或澄清函數和作業名稱中名詞和動詞的角色。 不過，請務必謹慎且一致地執行此動作。

    - **如下：** 表示函式的輸入和輸出代表相同的資訊，但輸出會將該資訊表示 **為** *X* ，而不是其原始標記法。 這特別適用于型別轉換函數。

      *範例：*
      - `IntAsDouble(2)` 指出輸入 (`2`) 和輸出 (`2.0`) 表示品質相同的資訊，但使用不同的 Q \# 資料類型來進行這項操作。

    - **來源：** 為了確保一致性，此介係詞   **不應該** 用來指出類型轉換函式或任何其他 **適合的情況** 。

    - ⛔️ **為：** **不應** 使用這個介係詞，以避免在許多程式設計語言中，將其使用方式與動詞混淆。
