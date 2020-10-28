---
title: 中的運算式 Q#
description: 瞭解如何在中指定、參考和合併常數、變數、運算子、作業和函數 Q# 。
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: e95a7cb9b74136ef9a6f51b4bbc32d1d93c43a0d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691598"
---
# <a name="expressions-in-no-locq"></a>中的運算式 Q#

## <a name="numeric-expressions"></a>數值運算式

數值運算式是、或類型的運算式 `Int` `BigInt` `Double` 。
亦即，它們可以是整數或浮點數。

`Int` 中的常值 Q# 會寫入為一系列的數位。
以和前置詞分別支援和寫入十六進位和二進位整數 `0x` `0b` 。

`BigInt` 中的常值 Q# 具有尾端或後置詞 `l` `L` 。
以 "0x" 前置詞支援和寫入十六進位大整數。
因此，下列是常值的所有有效用法 `BigInt` ：

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double` 中的常 Q# 值是使用小數位數寫入的浮點數。
您可以使用或不含小數點、或 `.` 以 ' e ' 或 ' e (' 表示的指數部分來撰寫它們，但在這種情況下，只有可能的負號和小數位數是有效的) 。
以下是有效的 `Double` 常值： `0.0` 、 `1.2e5` 、 `1e-5` 。

如果有任何專案類型的陣列運算式，您可以使用內 `Int` 建函數來形成運算式 [`Length`](xref:Microsoft.Quantum.Core.Length) ，並以括弧括住陣列運算式。
例如，如果系結 `a` 至陣列，則 `Length(a)` 為整數運算式。
如果 `b` 是整數陣列的陣列， `Int[][]` 則 `Length(b)` 為中的子陣列數目， `b` 而 `Length(b[1])` 是中第二個子陣列中的整數數目 `b` 。

假設有兩個相同類型的數值運算式，則二元運算子 `+` 、、 `-` 和可用 `*` `/` 來形成新的數值運算式。
新運算式的型別與組成運算式的類型相同。

假設有兩個整數運算式，請使用二元運算子 `^` (power) 來形成新的整數運算式。
同樣地，您也可以使用 `^` with 兩個雙精度浮點數運算式來形成新的雙精度浮點數運算式。
最後，您可以使用 `^` 左邊的大整數和右邊的整數來形成新的大整數運算式。
在此情況下，第二個參數必須符合32位;如果沒有，則會引發執行階段錯誤。

假設有兩個整數或大整數運算式，則會使用 `%` (模數) 、 `&&&` (位 and) 、 `|||` (位 or) 或 `^^^` (位 XOR) 運算子來形成新的整數或大整數運算式。

指定左邊的整數或大整數運算式，以及右邊的整數運算式時，請使用 `<<<` (算術左移) 或 `>>>` (算術右移) 運算子來建立新的運算式，其類型與左邊的運算式相同。

第二個參數 (移位量) 的移位量必須大於或等於零;負移位數量的行為未定義。
Shift 作業的移位量也必須符合32位;如果沒有，則會引發執行階段錯誤。
如果移位的數位是整數，則會解釋移位量，也 `mod 64` 就是1與65的位移具有相同的效果。

針對整數和大整數值，移位是算術。
將負數值向左或向右移位會產生負數。
亦即，將一個步驟向左或向右移動，會分別與相乘或除以2相同。

整數除法和整數模數會遵循與 c # 相同的負數行為。 也就是說， `a % b` 一律具有相同的正負號 `a` ，且 `b * (a / b) + a % b` 一律等於 `a` 。 例如：

|`A` | `B` | `A / B` | `A % B`|
|:---------:|:----------:|:---------:|:---------:|
| 5 | 2 | 2 | 1 |
| 5 | -2 | -2 | 1 |
| -5 | 2 | -2 | -1 |
| -5 | -2 | 2 | -1 |

大整數除法和模數運算的運作方式相同。

假設有任何數值運算式，您可以使用一元運算子來形成新的運算式 `-` 。
新的運算式與組成運算式的類型相同。

假設有任何整數或大整數運算式，您可以使用 `~~~` (位補數) 一元運算子來形成相同型別的新運算式。

## <a name="boolean-expressions"></a>布林運算式

這兩個 `Bool` 常值為 `true` 和 `false` 。

假設有兩個相同基本型別的運算式， `==` 就可以 `!=` 使用和二元運算子來建立 `Bool` 運算式。
如果兩個運算式相等，則運算式為 true，否則為 false。

使用者自訂類型的值可能不會進行比較，只能比較其未包裝的值。 例如，使用「解除包裝」運算子 `!` (在) 的[類型 Q# ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)中詳細說明。

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

值的相等比較是身分識別 `Qubit` 相等，也就是兩個運算式是否識別相同的量子位。
這兩個量子位的狀態不會進行比較、存取、測量或修改。

值的相等比較 `Double` 可能會因為四捨五入效果而產生誤導。
例如： `49.0 * (1.0/49.0) != 1.0` 。

假設有兩個數值運算式，則二元運算子 `>` 、 `<` 、和可用 `>=` `<=` 來建立新的布林運算式，如果第一個運算式分別大於、小於、大於或等於或小於或等於第二個運算式，則為 true。

假設有兩個布林運算式，請使用 `and` 二元運算子來建立新的布林運算式，如果兩個運算式都是 true，則為 true。 同樣地， `or` 如果兩個運算式中的任一個都是 true，則使用運算子會建立一個 true 的運算式。

假設有任何布林運算式， `not` 一元運算子可用來建立新的布林運算式，如果組成運算式為 false，則為 true。

## <a name="string-expressions"></a>字串運算式

Q# 允許在語句中使用字串 `fail` (在 [控制流程](xref:microsoft.quantum.guide.controlflow#fail-statement)) 和標準函式中所述 [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) 。 後者的特定行為取決於使用的模擬器，但通常會在程式期間呼叫時，將訊息寫入主機主控台 Q# 。

中的字串 Q# 是常值或字串插值。

字串常值類似于大部分語言中的簡單字串常值：以雙引號括住的 Unicode 字元序列 `" "` 。
在字串內，請使用反斜線字元 `\` 來將雙引號字元 (`\"`) ，或插入新行 ( ) 、換行字元 `\n` () ，或索引標籤 `\r` (`\t`) 。
例如：

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>插入字串

Q#字串插補的語法是 c # 語法的子集。 以下是其相關的重點 Q# ：

* 若要將字串常值識別為插入字串，請在其前面加上 `$` 符號。 `$`與開始字串常值的之間不能有空白字元 `"` 。

* 以下是使用 [`Message`](xref:Microsoft.Quantum.Intrinsic.Message) 函數將測量結果與其他運算式一起寫入至主控台的基本範例 Q# 。

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* 任何有效 Q# 的運算式可能會出現在字串插值中。

* 字串插值中的運算式會遵循 Q# 語法，而不是 c # 語法。 最顯著的差異在於不 Q# 支援逐字 (多行) 插入字串。

如需 c # 語法的詳細資訊，請參閱插入 [*字串*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。

## <a name="range-expressions"></a>範圍運算式

假設有三個 `Int` 運算式 `start` 、 `step` 和 `stop` ，則運算式 `start .. step .. stop` 是一個範圍運算式，其第一個元素為 `start` ，第二個元素是 `start+step` ，第三個元素是 `start+step+step` ，依此類推，直到您通過為止 `stop` 。
例如，如果是正數和，範圍可能是空的 `step` `stop < start` 。

範圍在兩端都包含在內。 也就是說，如果和之間的差異 `start` `stop` 是的整數倍數，則 `step` 範圍的最後一個專案會是 `stop` 。

假設有兩個 `Int` 運算式 `start` 和，則 `stop` 運算式 `start .. stop` 是等於的範圍運算式 `start .. 1 .. stop` 。
請注意， `step` 即使 `stop` 小於 `start` ; 在這種情況下，隱含是 + 1，範圍是空的。

部分範例範圍如下：

- `1..3` 是範圍1、2、3。
- `2..2..5` 為範圍2、4。
- `2..2..6` 為範圍2、4、6。
- `6..-2..2` 為6、4、2的範圍。
- `2..1` 是空的範圍。
- `2..6..7` 為範圍2。
- `2..2..1` 是空的範圍。
- `1..-1..2` 是空的範圍。

## <a name="qubit-expressions"></a>量子位運算式

唯一的 `Qubit` 運算式是系結至 `Qubit` 陣列值或陣列元素的符號 `Qubit` 。
沒有常值 `Qubit` 。

## <a name="pauli-expressions"></a>Pauli 運算式

四個 `Pauli` 值（、、 `PauliI` `PauliX` `PauliY` 和 `PauliZ` ）都是有效的 `Pauli` 運算式。

除了這樣，唯一的 `Pauli` 運算式是系結至 `Pauli` 陣列值或陣列元素的符號 `Pauli` 。

## <a name="result-expressions"></a>結果運算式

這兩個 `Result` 值 `One` `Zero` 都是有效的 `Result` 運算式。

除了這樣，唯一的 `Result` 運算式是系結至 `Result` 陣列值或陣列元素的符號 `Result` 。
請特別注意，與 `One` 整數不同的是 `1` ，它們之間並沒有直接的轉換。
和也是如此 `Zero` `0` 。

## <a name="tuple-expressions"></a>元組運算式

元組常值是適當類型的元素運算式序列（以逗號分隔），並以括弧括住。
例如， `(1, One)` 是 `(Int, Result)` 運算式。

除了常值以外，唯一的元組運算式是系結至元組值的符號、元組陣列的陣列元素，以及傳回元組的可呼叫調用。

## <a name="user-defined-type-expressions"></a>User-Defined 類型運算式

使用者定義型別的常值包含型別名稱，後面接著型別的基底元組類型的元組常值。
例如，如果 `IntPair` 是根據的使用者定義型別，則 `(Int, Int)` `IntPair(2, 3)` 是該類型的有效常值。

除了常值以外，唯一的使用者定義型別運算式是系結至該類型值的符號、該類型陣列的陣列元素，以及傳回該類型的可呼叫調用。

## <a name="unwrap-expressions"></a>解除包裝運算式

在中，解除包裝 Q# 運算子是尾端驚嘆號 `!` 。
例如，如果 `IntPair` 是具有基礎類型的使用者定義型別， `(Int, Int)` 而且 `s` 是具有值的變數，則 `IntPair(2, 3)` `s!` 為 `(2, 3)` 。

針對其他使用者定義型別所定義的使用者定義型別，您可以重複解除包裝運算子。 例如， `s!!` 表示的雙重解除包裝值 `s` 。
因此，如果 `WrappedPair` 是具有基礎類型的使用者定義型別 `IntPair` ，而且 `t` 是具有值的變數 `WrappedPair(IntPair(1,2))` ，則 `t!!` 為 `(1,2)` 。

運算子的優先順序高於除 `!` `[]` 陣列索引和切割以外的其他所有運算子。
`!` 然後系結 `[]` positionally; 也就是說， `a[i]![3]` 會讀取為 `((a[i])!)[3]` ： take 的 `i` 第一個專案 `a` ，將它解除包裝，然後取得未包裝值的第三個元素 (必須是陣列) 。

運算子的優先順序 `!` 有一個可能不明顯的影響。
如果函式或作業傳回的值接著會解除包裝，則函式或作業呼叫必須以括弧括住，讓引數元組系結至呼叫，而不是解除包裝。
例如：

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>陣列運算式

陣列常值是以逗號分隔的一或多個元素運算式的序列，並以方括弧括住 `[]` 。
所有元素都必須與相同的類型相容。

假設有兩個相同類型的陣列，請使用二元 `+` 運算子來形成新的陣列，這是兩個數組的串連。
例如：`[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`。

### <a name="array-creation"></a>陣列建立

假設有型別和 `Int` 運算式，請使用 `new` 運算子來配置指定大小的新陣列。
例如，配置 `new Int[i + 1]` `Int` 具有元素的新陣列 `i + 1` 。

不允許空的陣列常值（例如 `[]` ）。
相反地，您可以使用建立長度為零的陣列 `new T[0]` ，其中 `T` 是適合的型別預留位置。

新陣列的元素會初始化為類型相依的預設值。
在大部分的情況下，這會是零的變化。

對於實體參考的量子位和 callables，沒有合理的預設值。
因此，對於這些型別，預設值是不正確參考，您無法使用而不會造成執行階段錯誤，類似于 c # 或 JAVA 等語言中的 null 參考。
包含量子位或 callables 的陣列必須使用非預設值來初始化，才能安全地使用其專案。 如需適當的初始化常式，請參閱 <xref:Microsoft.Quantum.Arrays> 。

每個類型的預設值為：

類型 | 預設
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _不正確量子位_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | 空白範圍， `1..1..0`
 `Callable` | _調用無效_
 `Array['T]` | `'T[0]`

元組類型會依元素初始化元素。


### <a name="array-elements"></a>陣列元素

指定陣列運算式和運算式之後 `Int` ，會使用陣列元素運算子來形成新的運算式 `[]` 。
新運算式的類型與陣列的元素類型相同。
例如，如果系結 `a` 至類型的陣列，則 `Double` `a[4]` 為 `Double` 運算式。

如果陣列運算式不是簡單的識別碼，您必須將它括在括弧中，以選取專案。
例如，如果 `a` 和 `b` 都是類型的陣列 `Int` ，則串連的元素會以下列方式表示：

```qsharp
(a + b)[13]
```

中的所有陣列 Q# 都是以零為基底。
亦即，陣列的第一個元素 `a` 一律為 `a[0]` 。


### <a name="array-slices"></a>陣列配量

指定陣列運算式和運算式之後 `Range` ，會使用陣列配量運算子來形成新的運算式 `[ ]` 。
新的運算式與陣列的類型相同，而且包含依的專案（依所定義的順序）編制索引的陣列專案 `Range` `Range` 。
例如，如果系結 `a` 至類型的陣列，則 `Double` `a[3..-1..0]` 是 `Double[]` 包含前四個專案的運算式， `a` 但會依它們出現在中的相反順序 `a` 。

如果 `Range` 是空的，則產生的陣列配量為零長度。

就像參考陣列元素一樣，如果陣列運算式不是簡單的識別碼，您必須將它括在括弧中，以進行配量。
例如，如果 `a` 和 `b` 都是類型的陣列 `Int` ，則串連的配量會以下列方式表示：

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>推斷的開始/結束值

從 [0.8 版](xref:microsoft.quantum.relnotes)開始，我們支援範圍切割的內容運算式。 尤其是，您可以在範圍切割運算式的內容中省略範圍開始和結束值。 在這種情況下，編譯器會套用下列規則，以推斷範圍的預期分隔符號：

* 如果省略範圍 *開始* 值，則推斷開始值
  * 如果未指定任何步驟，或指定的步驟是正數，則為零。  
  * 如果指定的步驟為負數，則為配量陣列的長度減一。

* 如果省略範圍 *結束* 值，則推斷結束值
  * 如果未指定任何步驟，或指定的步驟是正數，則為配量陣列的長度減一。
  * 如果指定的步驟為負數，則為零。

部份範例如下：

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a>複製和更新運算式

由於所有 Q# 型別都是實值型別 (量子位採用有點特殊的角色) ，因此當值系結至符號或重新系結符號時，就會建立「複製」。 也就是說，的行為與 Q# 使用指派運算子建立複本的行為相同。 

當然，在實務上，只會視需要重新建立相關的部分。 這會影響您複製陣列的方式，因為不可能更新陣列專案。 若要修改現有的陣列，需要利用 *複製和更新* 機制。

您可以透過使用運算子和的 *複製和更新* 運算式，從現有的陣列建立新的陣列 `w/` `<-` 。
複製和更新運算式是表單的運算式 `expression1 w/ expression2 <- expression3` ，其中

* `expression1` 必須是類型 `T[]` 的類型 `T` 。
* `expression2` 定義中指定要修改之陣列中的哪些索引 `expression1` 。 `expression2` 必須是類型 `Int` 或類型 `Range` 。
* `expression3` 這是 `expression1` 根據中指定的索引，用來更新中之專案)  (s 的值 `expression2` 。 如果 `expression2` 是類型 `Int` ， `expression3` 必須為類型 `T` 。 如果 `expression2` 是類型 `Range` ， `expression3` 必須為類型 `T[]` 。

例如，複製和更新運算式 `arr w/ idx <- value` 會在中建立一個新的陣列，其中所有專案都會設定為中的對應元素 `arr` ，但 () 所指定的專案 `idx` ，其會設定為中) 的值 (`value` 。 

指定 `arr` 的包含陣列 `[0,1,2,3]` ，然後 

- `arr w/ 0 <- 10` 是陣列 `[10,1,2,3]` 。
- `arr w/ 2 <- 10` 是陣列 `[0,1,10,3]` 。
- `arr w/ 0..2..3 <- [10,12]` 是陣列 `[10,1,12,3]` 。

#### <a name="copy-and-update-expressions-for-named-items"></a>已命名專案的複製和更新運算式

使用者定義型別中的命名專案有類似的運算式。 

例如，請考慮類型 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
如果 `c` 包含類型的值 `Complex(1., -1.)` ，則 `c w/ Re <- 0.` 為 `Complex` 評估為之類型的運算式 `Complex(0., -1.)` 。

### <a name="jagged-arrays"></a>不規則陣列

不規則陣列（有時稱為「陣列陣列」）是其元素為數組的陣列。
不規則陣列的元素可以是不同的大小。
下列範例示範如何宣告和初始化表示乘法資料表的不規則陣列。

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a>Callables 的陣列 

您也可以建立 callables 的陣列。

* 如果通用元素類型是作業或函式類型，則所有專案都必須具有相同的輸入和輸出類型。
* 陣列的元素類型支援所有元素所支援的任何 [函子](xref:microsoft.quantum.guide.operationsfunctions) 。
例如，如果 `Op1` 、 `Op2` 和都 `Op3` 是 `Qubit[] => Unit` 作業，但是 `Op1` 支援、，而且支援 `Adjoint` `Op2` `Controlled` `Op3` 兩者：
  * `[Op1, Op2]` 是作業的陣列 `(Qubit[] => Unit)` 。
  * `[Op1, Op3]` 是作業的陣列 `(Qubit[] => Unit is Adj)` 。
  * `[Op2, Op3]` 是作業的陣列 `(Qubit[] => Unit is Ctl)` 。

不過，雖然作業 `(Qubit[] => Unit is Adj)` 和  `(Qubit[] => Unit is Ctl)` 具有的通用基底類型 `(Qubit[] => Unit)` ，但這些作業的 *陣列* 不會共用通用基底類型。

例如， `[[Op1], [Op2]]` 目前會引發錯誤，因為它會嘗試建立兩個不相容的陣列類型 `(Qubit[] => Unit is Adj)[]` 和中的陣列 `(Qubit[] => Unit is Ctl)[]` 。

如需 callables 的詳細資訊，請參閱這個頁面上的可呼叫[運算式](#callable-expressions)或[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="conditional-expressions"></a>條件運算式

假設有兩個相同類型和布林運算式的運算式，則會使用問號、和分隔號來形成條件運算式 `?` `|` 。 `a==b ? c | d`若為 true，則為條件運算式的值，如果為 false，則為 `c` `a==b` `d` 。

### <a name="conditional-expressions-with-callables"></a>使用 callables 的條件運算式

條件運算式可能會評估為具有相同輸入和輸出但支援不同函子的作業。 在此情況下，條件運算式的類型是具有輸入和輸出的作業，可支援這兩個運算式所支援的任何函子。
例如，如果 `Op1` 、 `Op2` 和都 `Op3` 是 `Qubit[]=>Unit` ，但 `Op1` 支援 `Adjoint` `Op2` `Controlled` `Op3` 、和兩者都支援：

- `flag ? Op1 | Op2` 這是一項作業 `(Qubit[] => Unit)` 。
- `flag ? Op1 | Op3` 這是一項作業 `(Qubit[] => Unit is Adj)` 。
- `flag ? Op2 | Op3` 這是一項作業 `(Qubit[] => Unit is Ctl)` 。

如果有兩個可能的結果運算式包括函數或作業呼叫，則只有在該結果是呼叫值的情況下，該呼叫才會發生。 例如，在此情況下，如果是 true，則會叫用作業 `a==b ? C(qs) | D(qs)` `a==b` `C` ，如果是 false，則只會叫用作業 `D` 。 這種方法類似于其他語言的 *簡短* 運算。

## <a name="callable-expressions"></a>可呼叫的運算式

可呼叫的常值是在編譯範圍中定義之作業或函式的名稱。 例如， `X` 是參考標準程式庫作業的作業常值 `X` ，而且 `Message` 是參考標準程式庫函數的函式常值 `Message` 。

如果作業支援 `Adjoint` 仿函數，則為作業 `Adjoint op` 運算式。
同樣地，如果作業支援 `Controlled` 仿函數，則 `Controlled op` 為作業運算式。
如需這些運算式類型的詳細資訊，請參閱 [呼叫](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)作業特製化。

函子 (`Adjoint` 和 `Controlled`) 系結比其他所有運算子更緊密，除了解除包裝運算子 `!` 和的陣列索引之外 `[ ]` 。
因此，下列各項都是有效的，前提是這些作業支援所使用的函子：

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>類型參數化可呼叫運算式

您可以使用可呼叫常值做為值，例如，將它指派給變數或將它傳遞給另一個可呼叫。 在此情況下，如果可呼叫的具有 [類型參數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)，您就必須提供參數作為可呼叫值的一部分。

可呼叫的值不能有任何未指定的型別參數。 例如，如果是具有簽章的函式 `Fun` `'T1->Unit` ：

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>可呼叫調用運算式

假設有一個可呼叫的運算式 (作業或函式) ，以及可呼叫的簽章之輸入類型的元組運算式，您可以藉由將元組運算式附加至可呼叫的運算式，來形成 *調用運算式* 。
調用運算式的類型是可呼叫之簽章的輸出類型。

例如，如果是具有簽章的作業 `Op` `((Int, Qubit) => Double)` ， `Op(3, qubit1)` 則為類型的運算式 `Double` 。
同樣地，如果是具有簽章的函 `Sin` `(Double -> Double)` `Sin(0.1)` 式，則為類型的運算式 `Double` 。
最後，如果是具有簽章的函式 `Builder` `(Int -> (Int -> Int))` ，則 `Builder(3)` 是從 `Int` 到 `Int` 的函式。

叫用可呼叫值運算式的結果需要一組額外的括弧來括住可呼叫的運算式。
因此，若要叫 `Builder` 用從上一個段落呼叫的結果，正確的語法為：

```qsharp
(Builder(3))(2)
```

叫用 [型別參數化](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) 可呼叫時，您可以在可呼叫的運算式之後，于角括弧內指定實際的型別參數 `< >` 。
這通常不是必要動作，因為 Q# 編譯器會推斷實際的類型。
但是，如果未指定型別參數化引數， [部分應用程式](xref:microsoft.quantum.guide.operationsfunctions#partial-application)*就* 需要它。
將具有不同仿函數支援的作業傳遞給可呼叫的時，它也很有用。

例如，如果有簽章，而且有簽章和簽章，則 `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` `Op2` 會 `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` `Func` 使用 `Op1` 做為第一個引數做為第二個引數，並做為第三個引數 `Op2` `Op3` ：

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

類型規格是必要的 `Op3` ，因為和 `Op1` 具有不同的類型，因此編譯器會將此視為不明確的，而不會有規格。


## <a name="operator-precedence"></a>運算子優先順序

* 除了之外，所有二元運算子都是右向關聯 `^` 。

* 括弧，如果是 `[ ]` 陣列切割和索引，請在任何運算子之前系結。

* `Adjoint` `Controlled` 陣列索引之後，但在所有其他運算子之前的函子和系結。

* 作業和函式呼叫的括弧也會在任何運算子之前系結，但在陣列索引和函子之後。

Q# 依優先順序排列的運算子，從最高到最低：

運算子 | 元 | 描述 | 運算元類型
---------|----------|---------|---------------
 尾隨 `!` | 一元 | 解除包裝 | 任何使用者定義型別
 `-`, `~~~`, `not` | 一元 | 數值負、位補數、邏輯否定 | `Int`、 `BigInt` 或適用于 `Double` `-` `Int` `BigInt` `~~~` `Bool``not`
 `^` | Binary | 整數乘冪 | `Int`或 `BigInt` 作為指數的基底 `Int`
 `/`, `*`, `%` | Binary | 除法、乘法、整數模數 | `Int`、 `BigInt` `Double` 適用于 `/` 和 `*` 的 `Int` 、 `BigInt` 或 `%`
 `+`, `-` | Binary | 加法或字串和陣列串連，減法 | `Int`、 `BigInt` 或 `Double` 、或 `String` 的任何陣列類型 `+`
 `<<<`, `>>>` | Binary | 左移、右移右移 | `Int` 或 `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | 小於、小於或等於、大於、大於或等於比較的比較結果 | `Int`、`BigInt` 或 `Double`
 `==`, `!=` | Binary | 相等、不等於比較 | 任何基本類型
 `&&&` | Binary | 位元 AND | `Int` 或 `BigInt`
 `^^^` | Binary | 位元 XOR | `Int` 或 `BigInt`
 <code>\|\|\|</code> | Binary | 位元 OR | `Int` 或 `BigInt`
 `and` | Binary | 邏輯 AND | `Bool`
 `or` | Binary | 邏輯 OR | `Bool`
 `..` | Binary/三元 | 範圍運算子 | `Int`
 `?` `|` | 三元 | 條件式 | `Bool` 針對左手邊
`w/` `<-` | 三元 | 複製和更新 | 請參閱 [複製和更新運算式](#copy-and-update-expressions)

## <a name="next-steps"></a>後續步驟

現在您可以使用中的運算式 Q# ，請移至[中的 Q# 作業和](xref:microsoft.quantum.guide.operationsfunctions)函式，以瞭解如何定義和呼叫作業和函數。
