---
title: 'Microsoft 問 # 樣式指南'
description: '瞭解 Q # 程式和程式庫的命名、輸入、檔和格式設定慣例。'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: f8e398b5c9932a5079222fed7ad20e54de814eb8
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274508"
---
# <a name="q-style-guide"></a>問 # 樣式指南 #
## <a name="general-conventions"></a>一般慣例 ##

本指南中所建議的慣例旨在協助您更容易閱讀和瞭解以 Q # 撰寫的程式和程式庫。

## <a name="guidance"></a>指引

我們建議：

- 絕對不要忽略慣例，除非您故意這麼做，才能為使用者提供更容易閱讀且易於理解的程式碼。

## <a name="naming-conventions"></a>命名規範 ##

在提供配量開發工具組的同時，我們致力於功能和作業名稱，協助量子開發人員撰寫容易閱讀的程式，並將驚訝降到最低。
其中一個重要的部分是，當我們選擇函式、作業和類型的名稱時，我們會建立程式設計人員用來表達量子概念的*詞彙*;透過我們的選擇，我們可以協助或妨礙他們的工作，以清楚溝通。
這會讓我們負責確保引進的名稱提供清楚明瞭，而不是隱匿。
在本節中，我們將詳細說明如何根據明確指引來達成此義務，以協助我們發揮問 # 開發小組的最佳效能。

### <a name="operations-and-functions"></a>作業和函式 ###

名稱應該建立的第一件事，就是指定的符號是否代表函式或作業。
函式和作業之間的差異，對於瞭解程式碼區塊的行為非常重要。
若要將函式和作業之間的區別傳達給使用者，我們需要使用副作用來處理該問答模組的配量作業。
也就是說，作業*會執行*某些動作。

相反地，函數會描述資料之間的數學關聯性。
運算式 `Sin(PI() / 2.0)` *是* `1.0` ，而不表示程式或其 qubits 的狀態。

總結而言，作業會在函式的情況下執行工作。
這種區別意味著我們將作業命名為動詞和函式做為名詞。

> [!NOTE]
> 當宣告使用者定義型別時，會同時隱含地定義用來建立該型別之實例的新函數。
> 從該觀點來看，使用者定義型別應該命名為名詞，讓類型本身和函式函數具有一致的名稱。

在合理的情況下，請確定作業名稱的開頭為動詞，以清楚指出作業所採取的效果。
例如：

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

有一個值得特別提及的案例，就是當作業接受另一個作業做為輸入並呼叫它時。
在這種情況下，當定義外部作業時，輸入作業所採取的動作並不明確，因此不會立即清除正確的動詞。
我們建議動詞 `Apply` ，如同在 `ApplyIf` 、和中 `ApplyToEach` `ApplyToFirst` 。
在此情況下，其他動詞也可能很有用，如中所示 `IterateThroughCartesianPower` 。

| 動詞命令 | 預期的效果 |
| ---- | ------ |
| 套用 | 提供做為輸入的作業稱為 |
| Assert | 模擬器會檢查可能的量子測量結果的假設 |
| Estimate | 傳回的是傳統值，代表從一個或多個度量所繪製的估計 |
| Measure | 會執行量子測量，並將其結果傳回給使用者 |
| 準備 | Qubits 的給定暫存器會初始化為特定狀態 |
| 範例 | 從某個分佈隨機傳回的傳統值 |

針對函式，我們建議避免使用動詞來取代常用名詞（請參閱以下有關名詞的指引）或形容詞：

- `ConstantArray`
- `Head`
- `LookupFunction`

特別的是，在幾乎所有情況下，我們建議使用過去的 participles，適當地指出函式名稱是強式連接到配量程式中其他位置的動作或副作用。
例如，會 `ControlledOnInt` 使用動詞 "control" 的部分分詞形式，指示函式做為修改其引數的形容詞。
這個名稱有額外的好處，可以比對內建仿函數的語義 `Controlled` ，如下所述。
同樣地，_代理程式名詞_也可以用來從作業名稱中建立函式和 UDT 名稱，就像 `Encoder` 是與強式相關聯的 UDT 名稱的情況一樣 `Encode` 。

# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- 使用動詞做為作業名稱。
- 使用名詞或形容詞作為函數名稱。
- 針對使用者定義的類型和屬性使用名詞。
- 針對所有可呼叫的名稱，請 `CamelCase` 在強式喜好設定中使用 `pascalCase` 、 `snake_case` 或 `ANGRY_CASE` 。 特別的是，請確定可呼叫的名稱是以大寫字母開頭。
- 針對所有區域變數，請 `pascalCase` 在強式喜好設定中使用 `CamelCase` 、 `snake_case` 或 `ANGRY_CASE` 。 特別的是，請確定本機變數是以小寫字母開頭。
- 避免在函式 `_` 和作業名稱中使用底線; 需要額外的階層層級，請使用命名空間和命名空間別名。

# <a name="examples"></a>[範例](#tab/examples)

|   | 名稱 | 描述 |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | 清除使用動詞（「反映」）來表示作業的效果。 |
| ☒ | <s>`operation XRotation`</s> | 使用名詞片語建議函式，而不是運算。 |
| ☒ | <s>`operation search_oracle`</s> | 使用 `snake_case` Contravenes Q # 標記法。 |
| ☒ | <s>`operation Search_Oracle`</s> | 使用底線 internal to operation name contravenes Q # 標記法。 |
| ☑ | `function StatePreparationOracle` | 使用名詞片語會建議函式傳回作業。 |
| ☑ | `function EqualityFact` | 清除使用名詞（"事實"）來表示這是函式，而是形容詞。 |
| ☒ | <s>`function GetRotationAngles`</s> | 使用動詞（"get"）表示這是一項作業。 |
| ☑ | `newtype GeneratorTerm` | 使用名詞片語清楚地指的是呼叫 UDT 函數的結果。 |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | 使用動詞命令時，建議 UDT 的函數是作業。 |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | 使用名詞片語會傳達屬性的使用。 |

***

### <a name="shorthand-and-abbreviations"></a>速記和縮寫 ###

前述的建議是，有許多形式的速記，會看到在量子運算中常見且普遍使用的用法。
我們建議您在存在的現有和通用速記位置使用它，特別是針對目的電腦作業內建的作業。
例如，我們選擇名稱 `X` ，而不是 `ApplyX` ，而 `Rz` 不是 `RotateAboutZ` 。
使用這類速記時，作業名稱應全部大寫（例如： `MAJ` ）。

在常用的縮寫和前列縮寫定義（例如 "QFT" 用於「量子傅立葉轉換」）中套用此慣例時，一定要特別注意。
我們建議遵循一般的 .NET 慣例，以使用完整名稱中的縮寫和前列縮寫定義，這規定：

- 兩個字母的縮寫和前列縮寫定義會以大寫（例如： `BE` "big endian"）命名，
- 所有較長的縮略字和前列縮寫定義都是在中命名 `CamelCase` （例如 `Qft` ，針對「量子傅立葉轉換」）

因此，執行 QFT 的作業可以稱為 `QFT` 速記，或寫出為 `ApplyQft` 。

對於特別常用的作業和函式，可能會想要提供縮寫名稱作為較長格式的_別名_：

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- 適當時，請考慮常用的已接受和廣泛使用的簡短名稱。
- 針對速記使用大寫。
- 使用大寫表示簡短（兩個字母）的縮寫和前列縮寫定義。
- 使用 `CamelCase` 更長（三個或更多個字母）的縮寫和前列縮寫定義。

# <a name="examples"></a>[範例](#tab/examples)

|   | 名稱 | 描述 |
|---|------|-------------|
| ☑ | `X` | 適用于「套用 $X $ 轉換」的清楚縮寫 |
| ☑ | `CNOT` | 「受控制-不」的易懂速記 |
| ☒ | <s>`Cnot`</s> | 速記不應位於 `CamelCase` 。 |
| ☑ | `ApplyQft` | Common initialism "QFT" 會顯示為完整格式名稱的一部分。 |
| ☑ | `QFT` | Common initialism "QFT" 會顯示為縮寫名稱的一部分。 |



***


### <a name="proper-nouns-in-names"></a>名稱中有適當名詞 ###

雖然在物理上，通常會在第一次發佈相關專案之後進行命名，但大部分的非 physicists 並不熟悉每個人的姓名和所有歷程記錄。
依賴物理的命名慣例可能會導致進入重大屏障，因為來自其他背景的使用者必須瞭解大量看似不透明的名稱，才能使用常見的作業和概念。
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
因此，我們建議在任何合理的情況下，將描述概念的一般名詞都採用強式喜好設定，以適當的名詞描述概念的發行歷程記錄。
在特定的範例中，單向控制的交換和雙向控制的非作業通常稱為學術文獻中的「Fredkin」和「Toffoli」作業，但是在 Q # 中識別的主要是 `CSWAP` 和 `CCNOT` 。
在這兩種情況下，API 檔批註都會根據適當名詞和所有適當的引文來提供同義字名稱。

這項喜好設定特別重要，因為一定要有一些適當名詞的使用方式，問 # 會遵循許多傳統語言所設定的傳統，並 `Bool` 參考布林邏輯參照中的型別，而這些類型在 George Boole 中會被命名為。
類似的一些量子概念會以類似的方式命名，包括 `Pauli` 問答 # 語言內建的類型。
藉由將適當名詞的使用方式降到最低，這種用法並不重要，我們會降低無法合理地避免適當名詞的影響。

# <a name="guidance"></a>[指引](#tab/guidance) 

我們建議：

- 避免在名稱中使用適當名詞。

# <a name="examples"></a>[範例](#tab/examples)

***

### <a name="type-conversions"></a>類型轉換 ###

由於 Q # 是強式和 staticly 型別語言，因此一種類型的值只能使用類型轉換函式的明確呼叫，當做另一個類型的值使用。
這與允許以隱含方式變更類型的語言（例如：類型升階）或透過轉換而成。
因此，型別轉換函式在 Q # 程式庫開發中扮演著重要的角色，並包含其中一個常見的命名相關決策。
不過，我們會注意到，因為型別轉換一律是_決定性_的，所以它們可以撰寫為函式，因此會落在上述建議之下。
特別的是，我們建議類型轉換函式絕不能命名為動詞（例如： `ConvertToX` ）或副詞介係詞片語（ `ToX` ），但應該命名為形容詞介係詞片語，以指出來源和目的地類型（ `XAsY` ）。
在類型轉換函式名稱中列出陣列類型時，我們建議速記 `Arr` 。
避免發生例外狀況時，我們建議使用來命名所有類型轉換函式， `As` 以便快速識別這些函數。

# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- 如果函式將類型的值轉換 `X` 成類型的值 `Y` ，請使用名稱 `AsY` 或 `XAsY` 。

# <a name="examples"></a>[範例](#tab/examples)

|   | 名稱 | 描述 |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | 介係詞 "to" 會產生動詞片語，表示作業，而不是函數。 |
| ☒ | <s>`AsDouble`</s> | 輸入類型不會從函式名稱中清除。 |
| ☒ | <s>`PauliArrFromBoolArr`</s> | 輸入和輸出類型以錯誤的順序出現。 |
| ☑ | `ResultArrAsBoolArr` | 輸入類型和輸出類型都是明確的。 |

***

### <a name="private-or-internal-names"></a>私用或內部名稱 ###

在許多情況下，名稱僅適用于程式庫或專案的內部使用，而且不是程式庫所提供之 API 的保證部分。
明確指出在命名函式和作業時，這是很有説明的，讓僅限內部程式碼的意外相依性變得顯而易見。
如果作業或函式不適合直接使用，而是應由部分應用程式所使用的相符可呼叫來使用，請考慮使用以關鍵字開頭的名稱， `internal` 以取得部分套用的可呼叫。

# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- 當函式、作業或使用者定義型別不屬於 Q # 程式庫或程式的公用 API 時，請在、或宣告前面放置關鍵字，以確定它已標記為內部 `internal` `function` `operation` `newtype` 。

# <a name="examples"></a>[範例](#tab/examples)

|   | 名稱 | 描述 |
|---|------|-------------|
| ☒ | <s>`operation _ApplyDecomposedOperation`</s> | 請勿使用底線 `_` 來表示此作業僅供內部使用。 |
| ☑ | `internal operation ApplyDecomposedOperation` | `internal`開頭的關鍵字清楚地表示此作業僅供內部使用。 |

***
### <a name="variants"></a>變異 ###

雖然這項限制可能不會在未來的 Q # 版本中持續存在，但目前還是通常會有一組相關的作業或函式，這些群組會根據其輸入支援的函子，或其引數的具體類型來區分。
這些群組可以使用相同的根名稱，後面接著一或兩個表示其 variant 的字母來加以區別。

| 後置詞 | 意義 |
|--------|---------|
| `A` | 預期支援的輸入`Adjoint` |
| `C` | 預期支援的輸入`Controlled` |
| `CA` | 預期支援 `Controlled` 和的輸入`Adjoint` |
| `I` | 輸入或輸入的類型為`Int` |
| `D` | 輸入或輸入的類型為`Double` |
| `L` | 輸入或輸入的類型為`BigInt` |

# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- 如果函式或作業與其輸入的型別和仿函數支援無關，則不會使用尾碼。
- 如果函式或作業是由其輸入的型別和仿函數支援所關聯的任何類似函式或運算，請使用上表中的尾碼來區別變體。

# <a name="examples"></a>[範例](#tab/examples)

***

### <a name="arguments-and-variables"></a>引數和變數 ###

函式或作業的 Q # 程式碼的主要目標，是為了方便閱讀和瞭解。
同樣地，輸入和類型引數的名稱應該會傳達函式或引數在提供後的使用方式。


# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- 針對所有變數和輸入名稱，請 `pascalCase` 在強式喜好設定中使用 `CamelCase` 、 `snake_case` 或 `ANGRY_CASE` 。
- 輸入名稱應該是描述性的;盡可能避免一或兩個字母名稱。
- 只接受一個型別引數的作業和函式應該會 `T` 在其角色很明顯時，表示該型別引數。
- 如果函式或作業接受多個類型引數，或如果單一類型引數的角色不明顯，請考慮針對每個類型使用前面加上的簡短大寫字組 `T` （例如： `TOutput` ）。
- 不包含引數和變數名稱中的類型名稱;這項資訊可以和應該由您的開發環境提供。
- 依其常值名稱（ `flagQubit` ）和陣列類型（以複數（））表示純量類型 `measResults` 。
  特別是針對 qubits 的陣列，請考慮以某種方式來表示這類類型，其 `Register` 名稱參照的 qubits 順序是密切相關的。
- 當做陣列索引使用的變數應該以為開頭 `idx` ，且應為單數（例如： `things[idxThing]` ）。
  特別是，強烈避免使用單字母變數名稱做為索引;請考慮 `idx` 至少使用。
- 用來保存陣列長度的變數應該以開頭 `n` ，而且應該是複數化（例如： `nThings` ）。

# <a name="examples"></a>[範例](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>名為 Items 的使用者定義型別 ###

使用者定義類型中的命名專案應該命名為 `CamelCase` ，即使在 UDT 的輸入中也一樣。
這有助於在使用存取子標記法（例如： `callable::Apply` ）或複製和更新標記法（）時，清楚地將命名的專案與本機範圍變數的參考區隔開 `set arr w/= Data <- newData` 。

# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- UDT 函式中的命名專案應該命名為 `CamelCase` ，也就是說，它們的開頭必須是大寫。
- 解析為作業的命名專案應該命名為動詞階段。
- 未解析為作業的命名專案應該命名為名詞片語。
- 針對包裝作業的 Udt，應定義名為的單一名為的專案 `Apply` 。

# <a name="examples"></a>[範例](#tab/examples)

|   | 程式碼片段 | 描述 |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | 名稱 `Apply` 是格式的 `CamelCase` 動詞片語，表示已命名的專案是一項作業。 |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | 命名專案的開頭必須是初始大寫字母。 |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | 解析為函式的命名專案應該命名為名詞片語，而不是動詞片語。 |

***

## <a name="input-conventions"></a>輸入慣例 ##

當開發人員呼叫作業或函式時，必須以特定順序指定該作業或函數的各種輸入，進而增加開發人員所面臨的認知負載，以便使用程式庫。
特別是，記住輸入排序的工作通常是來自手邊工作的干擾：程式設計配量演算法。
雖然豐富的 IDE 支援可以減輕這種情況，但良好的設計和遵循一般慣例也有助於將 API 所施加的認知負載降到最低。

可能的話，減少作業或函式所預期的輸入數目會很有説明，因此，每個輸入的角色對於呼叫該作業或函式的開發人員，以及稍後閱讀該程式碼的開發人員而言，會更容易察覺。
特別是當您無法或合理地減少作業或函式的引數數目時，一定要具有一致的順序，以將使用者在預測輸入順序時所面臨的驚訝降到最低。

我們建議輸入排序慣例，其主要衍生自將部分應用程式視為 currying f （x，y）≡ f （x）（y）的一般化。
因此，部分套用第一個引數應該會產生可呼叫的，這在合理的情況下會非常有用。
遵循此原則，請考慮使用下列引數順序：

- 傳統不可呼叫的引數，例如角度、冪向量等等。
- 可呼叫的引數（函數和引數）。
  如果函式和作業都做為引數，請考慮將作業放在函數之後。
- 由可呼叫引數處理的集合，其方式與 `Map` 、 `Iter` 、和相同 `Enumerate` `Fold` 。
- 當做控制項使用的 Qubit 引數。
- 當做目標使用的 Qubit 引數。

請考慮使用作業來 `ApplyPhaseEstimationIteration` 進行階段估計，此作業會採用角度和 oracle，將角度傳遞至 `Rz` 不同調整因數的陣列，然後控制 oracle 的應用程式。
我們會以 `ApplyPhaseEstimationIteration` 下列方式排序輸入：

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
基於將驚訝降到最低的特殊情況，某些函式和作業會模擬內建函子和的行為 `Adjoint` `Controlled` 。
例如， `ControlledOnInt<'T>` 具有 `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` 類似仿函數的類型， `ControlledOnInt<Qubit[]>(5, _)` `Controlled` 但在控制項暫存器代表 state $ \ket {5} = \ket $ 的條件上 {101} 。
因此，開發人員預期會將可 `ControlledOnInt` 呼叫的輸入放在最後進行轉換，而且產生的作業會採用與仿函數輸出相同的順序做為其輸入 `(Qubit[], 'T)` --- `Controlled` 。

# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- 使用與部分應用程式一致的輸入排序。
- 使用與內建函子一致的輸入排序。
- 將所有的傳統輸入放在任何量子輸入之前。

# <a name="examples"></a>[範例](#tab/examples)

***

## <a name="documentation-conventions"></a>文件集慣例 ##

Q # 語言可讓您透過使用特殊格式的檔批註，將檔附加至作業、函式和使用者定義類型。
以三斜線（）表示 `///` ，這些檔批註是小型的[DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)檔，可用來描述每個作業、函式和使用者定義類型的用途、每個所需的輸入等等。
配量開發工具組所提供的編譯器會將這些批註解壓縮，並使用它們來協助排版類似于的檔 https://docs.microsoft.com/quantum 。
同樣地，隨配量開發工具組提供的語言伺服器會使用這些批註，在使用者將滑鼠停留在其 Q # 程式碼的符號上方時提供協助。
藉由使用檔批註，可以讓使用者瞭解程式碼，方法是提供有用的參考，以取得使用本檔中的其他慣例無法輕鬆表示的詳細資料。

<div class="nextstepaction">
    [檔批註語法參考](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</div>

若要有效地使用此功能來協助使用者，建議您在撰寫檔批註時記住一些事項。

# <a name="guidance"></a>[指引](#tab/guidance)

我們建議：

- 每個公用函式、作業和使用者定義型別都應該緊接在檔批註前面。
- 每個檔批註至少應該包含下列區段：
    - 摘要
    - 輸入
    - 輸出（如果適用）
- 請確定所有摘要都是兩個句子或更少。 如果需要更多空間，請 `# Description` `# Summary` 以完整的詳細資料提供緊接在後面的區段。
- 在合理的情況下，請勿在摘要中包含數學運算，因為並非所有用戶端都支援摘要中的 TeX 標記法。 請注意，撰寫 prose 檔（例如 TeX 或 Markdown）時，最好使用較長的行長度。
- 在區段中提供所有相關的數學運算式 `# Description` 。
- 在描述輸入時，請勿重複每個輸入的類型，因為它們可以由編譯器推斷，而風險會造成不一致的情況。
- 提供適當的範例，每個都在自己的 `# Example` 區段中。
- 在列出程式碼之前，請先簡短地描述每個範例。
- 在一節中提及所有相關的學術刊物（例如：論文、訴訟、blog 文章和替代的執行方式），並以點 `# References` 符的連結清單來說明。
- 請確定在可能的情況下，所有引文連結都是永久和固定識別碼（DOIs 或已建立版本的 arXiv 號碼）。
- 當作業或函式透過仿函數變體與其他作業或函數相關時，請在區段中，將其他變體列出為專案符號 `# See Also` 。
- 在層級1（）區段之間保留空白的批註行 `/// #` ，但不要在層級2（）區段之間留下空白的一行 `/// ##` 。

# <a name="examples"></a>[範例](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>格式設定慣例 ##

除了上述的建議之外，也有助於讓程式碼盡可能清楚，以使用一致的格式化規則。
根據本質，這類格式規則通常是任意的，而且相當於個人美學。
儘管如此，我們建議您在共同作業者群組中維護一組一致的格式設定慣例，特別是針對大型 Q # 專案（例如，量子開發工具組本身）。
這些規則可以使用與 Q # 編譯器整合的格式工具自動套用。

# <a name="guidance"></a>[指引](#tab/guidance) 

我們建議：

- 使用四個空格，而不是可攜性的索引標籤。
  例如，在 VS Code：
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- 行在合理的79個字元。
- 在二元運算子前後使用空格。
- 在用於類型注釋的冒號兩邊使用空格。
- 在陣列和元組常值中使用逗號後面加上一個空格（例如，在函數和作業的輸入中）。
- 在函數、作業或 UDT 名稱之後，或在屬性宣告中的後面，請勿使用空格 `@` 。
- 每個屬性宣告都應該在自己的行上。

# <a name="examples"></a>[範例](#tab/examples)

|   | 程式碼片段 | 描述 |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | 在二元運算子前後使用空格。 |
| ☒ | <s>`target:Qubit`</s> | 在類型批註冒號前後使用空格。 |
| ☑ | `Example(a, b, c)` | 輸入元組中的專案會正確地分隔，以方便閱讀。 |
| ☒ | <s>`Example (a, b, c)`</s> | 在函數、作業或 UDT 名稱之後，應該隱藏空格。 |

***
