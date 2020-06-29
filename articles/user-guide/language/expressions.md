---
title: Q 中的類型運算式#
description: '瞭解如何指定、參考和合併常數、變數、運算子、作業和函數，做為 Q # 中的運算式。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 1821df6a3a51a62b44f3ccd96b127577c5db990a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415383"
---
# <a name="type-expressions-in-q"></a>Q 中的類型運算式#

## <a name="numeric-expressions"></a>數值運算式

數值運算式是、或類型的運算式 `Int` `BigInt` `Double` 。
也就是說，它們可以是整數或浮點數。

`Int`Q # 中的常值會寫入為一連串的數位。
以和前置詞分別支援和寫入十六進位和二進位整數 `0x` `0b` 。

`BigInt`Q # 中的常值具有尾端 `l` 或 `L` 尾碼。
支援十六進位大整數，並以 "0x" 前置詞寫入。
因此，下列是常值的所有有效用法 `BigInt` ：

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`Q # 中的常值是使用十進位數撰寫的浮點數。
它們可以使用或不含小數點、 `.` ，或以 ' e ' 或 ' e ' 表示的指數部分（之後只有可能的負號和十進位數有效）來撰寫。
下列是有效的 `Double` 常值： `0.0` 、 `1.2e5` 、 `1e-5` 。

假設有任何元素類型的陣列運算式，您可以使用內 `Int` 建函數來形成運算式 [`Length`](xref:microsoft.quantum.core.length) ，並以括弧括住陣列運算式。
例如，如果系結 `a` 至陣列，則 `Length(a)` 為整數運算式。
如果 `b` 是整數陣列的陣列， `Int[][]` 則 `Length(b)` 是中的子陣列數目 `b` ，而 `Length(b[1])` 是中第二個子陣列中的整數數目 `b` 。

假設有兩個相同類型的數值運算式，則 `+` 可以使用二元運算子、、 `-` `*` 和 `/` 來形成新的數值運算式。
新運算式的類型與組成運算式的類型相同。

假設有兩個整數運算式，請使用二元運算子 `^` （乘冪）來形成新的整數運算式。
同樣地，您也可以使用搭配 `^` 兩個雙重運算式來形成新的 double 運算式。
最後，您可以使用 `^` 左邊的大整數和右邊的整數來形成新的大整數運算式。
在此情況下，第二個參數必須符合32位;如果不是，就會引發執行階段錯誤。

假設有兩個整數或大整數運算式，請使用 `%` （模數）、 `&&&` （位 and）、 `|||` （位 or）或 `^^^` （位 XOR）運算子來形成新的整數或大整數運算式。

指定左邊的整數或大整數運算式，以及右邊的整數運算式時，請使用 `<<<` （算術左移位）或 `>>>` （算術右移）運算子，建立與左邊運算式類型相同的新運算式。

轉換作業的第二個參數（移位量）必須大於或等於零;負位移金額的行為未定義。
任何移位作業的移位量也必須符合32位;如果不是，就會引發執行階段錯誤。
如果移位的數位是整數，則會解讀位移量 `mod 64` ; 也就是說，1和位移65的位移會有相同的效果。

對於整數和大整數值，移位是算術。
將負數值向左或向右移位會產生負數。
也就是說，將一個步驟向左或向右移位，會分別與乘法或除以2相同。

整數除法和整數模數會遵循與 c # 相同的負數行為。
也就是， `a % b` 一律具有相同的正負號 `a` ，而且 `b * (a / b) + a % b` 一律等於 `a` 。
例如：

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

大整數除法和模數運算的運作方式相同。

假設有任何數值運算式，您可以使用一元運算子來形成新的運算式 `-` 。
新的運算式與組成運算式的類型相同。

假設有任何整數或大整數運算式，您可以使用 `~~~` （位補數）一元運算子來形成相同類型的新運算式。

## <a name="boolean-expressions"></a>布林運算式

這兩個 `Bool` 常值為 `true` 和 `false` 。

假設有兩個相同基本類型的運算式，則 `==` 和 `!=` 二元運算子可用來建立 `Bool` 運算式。
如果兩個運算式相等，則運算式為 true，否則為 false。

可能不會比較使用者定義類型的值，只可以比較其未包裝的值。 例如，使用「解除包裝」運算子（如需 `!` 詳細說明，請見[Q # 中的類型](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)）。

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

值的相等比較 `Qubit` 是識別相等的，也就是兩個運算式是否識別相同的 qubit。
這兩個 qubits 的狀態不會由這項比較進行比較、存取、測量或修改。

值的相等比較 `Double` 可能會因為進位效果而誤導。
例如： `49.0 * (1.0/49.0) != 1.0` 。

假設有兩個數值運算式， `>` `<` `>=` `<=` 如果第一個運算式分別大於、小於、大於或等於或小於或等於第二個運算式，則二元運算子、、和可能會用來建立新的布林值運算式。

假設有兩個布林運算式，請使用 `and` 二元運算子來建立新的布林運算式，如果兩個運算式都是 true，則為 true。 同樣地， `or` 如果兩個運算式的其中一個為 true，則使用運算子會建立 true 的運算式。

假設有任何布林運算式， `not` 一元運算子可用來建立新的布林運算式，如果組成運算式為 false，則為 true。

## <a name="string-expressions"></a>字串運算式

Q # 允許在 `fail` 語句（在[控制流程](xref:microsoft.quantum.guide.controlflow#fail-statement)中說明）和標準函式中使用字串 [`Message`](xref:microsoft.quantum.intrinsic.message) 。 後者的特定行為取決於所使用的模擬器，但通常會在問 # 程式期間呼叫時，將訊息寫入主機主控台。

Q # 中的字串可以是常值或字串插值。

字串常值類似于大部分語言中的簡單字串常值：以雙引號括住的 Unicode 字元序列 `" "` 。
在字串內，使用反斜線字元 `\` 來轉義雙引號字元（ `\"` ），或插入新行（ `\n` ）、回車（）或索引標籤 `\r` （ `\t` ）。
例如：

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a>插入字串

String 插補的 Q # 語法是 c # 語法的子集。 以下是與 Q # 相關的重點：

* 若要將字串常值識別為插入字串，請在其前面加上 `$` 符號。 `$`開始字串常值的和之間不能有空白字元 `"` 。

* 以下是使用 [`Message`](xref:microsoft.quantum.intrinsic.message) 函數將測量結果寫入主控台的基本範例，以及其他的 Q # 運算式。

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* 任何有效的 Q # 運算式可能會出現在字串插值中。

* 插補字串內的運算式遵循 Q # 語法，而不是 c # 語法。 最明顯的差異在於，Q # 不支援逐字（多行）字串插值。

如需 c # 語法的詳細資訊，請參閱[*字串插值*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。

## <a name="range-expressions"></a>範圍運算式

假設有任何三個 `Int` 運算式 `start` 、 `step` 和 `stop` ，則運算式 `start .. step .. stop` 為範圍運算式，其第一個元素為 `start` 、第二個元素為 `start+step` 、第三個元素為 `start+step+step` ，依此類推，直到您通過為止 `stop` 。
例如，如果是正數和，範圍可能會是空的 `step` `stop < start` 。

範圍包含在兩端。 也就是說，如果和之間的差異 `start` `stop` 是的整數倍數 `step` ，則範圍的最後一個元素會是 `stop` 。

假設有兩個 `Int` 運算式 `start` 和 `stop` ，運算式 `start .. stop` 就是等於的範圍運算式 `start .. 1 .. stop` 。
請注意， `step` 即使小於，隱含也是 + 1 `stop` `start` ; 在這種情況下，範圍是空的。

一些範例範圍如下：

- `1..3`為1、2、3的範圍。
- `2..2..5`是範圍2，4。
- `2..2..6`為範圍2、4、6。
- `6..-2..2`為6、4、2的範圍。
- `2..1`這是空的範圍。
- `2..6..7`為範圍2。
- `2..2..1`這是空的範圍。
- `1..-1..2`這是空的範圍。

## <a name="qubit-expressions"></a>Qubit 運算式

唯一的 `Qubit` 運算式是系結至 `Qubit` 陣列的值或陣列元素的符號 `Qubit` 。
沒有任何 `Qubit` 常值。

## <a name="pauli-expressions"></a>Pauli 運算式

、、和這四個 `Pauli` 值 `PauliI` `PauliX` `PauliY` `PauliZ` 都是有效的 `Pauli` 運算式。

除了這以外，唯一的 `Pauli` 運算式是系結至 `Pauli` 陣列值或陣列元素的符號 `Pauli` 。

## <a name="result-expressions"></a>結果運算式

和這兩個 `Result` 值 `One` `Zero` 都是有效的 `Result` 運算式。

除了這以外，唯一的 `Result` 運算式是系結至 `Result` 陣列值或陣列元素的符號 `Result` 。
特別要注意的是，與 `One` 整數不相同 `1` ，而且它們之間沒有直接的轉換。
和的情況也是 `Zero` 如此 `0` 。

## <a name="tuple-expressions"></a>元組運算式

元組常值是適當類型的元素運算式序列，並以逗號分隔，並以括弧括住。
例如， `(1, One)` 是 `(Int, Result)` 運算式。

除了常值以外，唯一的元組運算式是系結至元組值的符號、元組陣列的陣列元素，以及傳回元組的可呼叫調用。

## <a name="user-defined-type-expressions"></a>使用者定義型別運算式

使用者自訂類型的常值是由類型名稱後面接著類型的基礎元組類型的元組常值所組成。
例如，如果 `IntPair` 是以為基礎的使用者定義型別 `(Int, Int)` ，則 `IntPair(2, 3)` 是該型別的有效常值。

除了常值以外，使用者定義型別的唯一運算式是系結至該型別、該型別陣列的陣列元素，以及傳回該型別之可呼叫調用的符號。

## <a name="unwrap-expressions"></a>解除包裝運算式

在 Q # 中，解除包裝運算子是尾端驚嘆號 `!` 。
例如，如果 `IntPair` 是具有基礎類型的使用者定義型別， `(Int, Int)` 而且是值為的 `s` 變數，則 `IntPair(2, 3)` `s!` 為 `(2, 3)` 。

針對其他使用者定義類型所定義的使用者定義型別，您可以重複解除包裝運算子。 例如， `s!!` 表示的雙重解除包裝值 `s` 。
因此，如果 `WrappedPair` 是具有基礎類型的使用者定義型別 `IntPair` ，而 `t` 是具有值的變數 `WrappedPair(IntPair(1,2))` ，則 `t!!` 為 `(1,2)` 。

除了 `!` 陣列索引和切割以外，運算子的優先順序高於其他所有運算子 `[]` 。
`!`和系結 `[]` positionally; 也就是 `a[i]![3]` 讀取為 `((a[i])!)[3]` ：取得的 `i` 第個元素 `a` ，將它解除包裝，然後取得未包裝值的第3個元素（必須是陣列）。

運算子的優先順序 `!` 有一個可能不明顯的影響。
如果函式或作業傳回值，因而解除包裝，則函式或作業呼叫必須以括弧括住，讓引數元組系結至呼叫，而不是系結。
例如：

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>陣列運算式

陣列常值是一系列的一或多個元素運算式，並以逗號分隔，並以方括弧括住 `[]` 。
所有元素都必須與相同的型別相容。

假設有兩個相同類型的陣列，請使用二元 `+` 運算子來形成新陣列，這是兩個數組的串連。
例如：`[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`。

### <a name="array-creation"></a>陣列建立

假設有類型和 `Int` 運算式，請使用 `new` 運算子來配置指定大小的新陣列。
例如，會配置 `new Int[i + 1]` `Int` 具有元素的新陣列 `i + 1` 。

不允許空的陣列常值（例如 `[]` ）。
相反地，您可以使用來建立長度為零的陣列 `new T[0]` ，其中 `T` 是適合類型的預留位置。

新陣列的元素會初始化為與類型相關的預設值。
在大部分的情況下，這會是零的部分變化。

對於實體參考的 qubits 和 callables 而言，沒有合理的預設值。
因此，在這些類型中，預設值是不會造成執行階段錯誤而無法使用的無效參考，類似于 c # 或 JAVA 等語言中的 null 參考。
包含 qubits 或 callables 的陣列必須使用非預設值進行初始化，才能安全地使用它們的元素。 如需適當的初始化常式，請參閱 <xref:microsoft.quantum.arrays> 。

每種類型的預設值為：

類型 | 預設
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | _不正確 qubit_
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | 空白範圍，`1..1..0`
 `Callable` | _可呼叫無效_
 `Array['T]` | `'T[0]`

元組類型會依元素初始化元素。


### <a name="array-elements"></a>陣列元素

假設有陣列運算式和 `Int` 運算式，請使用陣列元素運算子來形成新的運算式 `[]` 。
新運算式的類型與陣列的元素類型相同。
例如，如果系結 `a` 至類型的陣列，則 `Double` `a[4]` 為 `Double` 運算式。

如果陣列運算式不是簡單的識別碼，您必須將它括在括弧中，以選取元素。
例如，如果 `a` 和 `b` 都是類型的陣列 `Int` ，則串連中的元素會表示為：

```qsharp
(a + b)[13]
```

Q # 中的所有陣列都是以零為基底。
也就是說，陣列的第一個元素 `a` 一定是 `a[0]` 。


### <a name="array-slices"></a>陣列配量

假設有陣列運算式和 `Range` 運算式，請使用陣列配量運算子來形成新的運算式 `[ ]` 。
新的運算式與陣列具有相同的類型，並且包含以的專案編制索引的陣列專案（依照所 `Range` 定義的順序） `Range` 。
例如，如果系結 `a` 至類型的陣列，則 `Double` `a[3..-1..0]` 是 `Double[]` 包含前四個專案的運算式， `a` 但在中出現的順序則是相反的 `a` 。

如果 `Range` 是空的，則產生的陣列配量為零長度。

就像參考陣列專案一樣，如果陣列運算式不是簡單的識別碼，您必須將它括在括弧中以進行配量。
例如，如果 `a` 和 `b` 都是類型的陣列 `Int` ，則串連中的配量會表示為：

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a>推斷的開始/結束值

從[0.8 版](xref:microsoft.quantum.relnotes)開始，我們支援範圍切割的內容相關運算式。 特別是，您可能會在範圍切割運算式的內容中省略範圍開始和結束值。 在這種情況下，編譯器會套用下列規則，以推斷範圍的預期分隔符號：

* 如果省略範圍*起始*值，則推斷的起始值
  * 如果未指定任何步驟，或指定的步驟是正數，則為零。  
  * 如果指定的步驟是負數，則為已切割陣列的長度減一。

* 如果省略範圍*結束*值，則推斷的結束值
  * 如果未指定任何步驟，或指定的步驟是正數，則為已切割陣列的長度減一。
  * 如果指定的步驟是負數，則為零。

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

由於所有 Q # 型別都是實值型別（qubits 採用有點特殊的角色），因此，當值系結至符號或符號重新系結時，就會建立「複製」。 也就是說，問 # 的行為與使用指派運算子建立複本時相同。 

當然，在實務上，只有相關的部分會在需要時重新建立。 這會影響您複製陣列的方式，因為不可能更新陣列專案。 若要修改現有的陣列，您必須利用*複製和更新*機制。

您可以透過使用運算子和的「*複製並更新*」運算式，從現有的陣列建立新的陣列 `w/` `<-` 。
複製和更新運算式是格式的運算式 `expression1 w/ expression2 <- expression3` ，其中

* `expression1`必須是 `T[]` 某種類型的類型 `T` 。
* `expression2`定義在中指定要修改之陣列中的哪些索引 `expression1` 。 `expression2`必須是類型 `Int` 或類型 `Range` 。
* `expression3`這是 `expression1` 根據中指定的索引，用來更新中之元素的值 `expression2` 。 如果 `expression2` 是類型 `Int` ， `expression3` 必須是類型 `T` 。 如果 `expression2` 是類型 `Range` ， `expression3` 必須是類型 `T[]` 。

例如，copy 和 update 運算式 `arr w/ idx <- value` 會建立新的陣列，並將所有專案設定為中的對應專案 `arr` ，但所指定的元素除外 `idx` ，其設定為中的值 `value` 。 

指定 `arr` 的包含陣列 `[0,1,2,3]` ，然後 

- `arr w/ 0 <- 10`是陣列 `[10,1,2,3]` 。
- `arr w/ 2 <- 10`是陣列 `[0,1,10,3]` 。
- `arr w/ 0..2..3 <- [10,12]`是陣列 `[10,1,12,3]` 。

#### <a name="copy-and-update-expressions-for-named-items"></a>已命名專案的複製和更新運算式

使用者定義類型中的命名專案有類似的運算式。 

例如，請考慮類型 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
如果 `c` 包含型別的值 `Complex(1., -1.)` ，則 `c w/ Re <- 0.` 為評估為之型別的運算式 `Complex` `Complex(0., -1.)` 。

### <a name="jagged-arrays"></a>不規則陣列

不規則陣列（有時稱為「陣列」陣列）是其元素為數組的陣列。
不規則陣列的元素可以是不同的大小。
下列範例顯示如何宣告和初始化代表乘法資料表的不規則陣列。

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

* 如果一般專案類型是作業或函式類型，所有元素都必須具有相同的輸入和輸出類型。
* 陣列的元素類型支援所有元素都支援的任何[函子](xref:microsoft.quantum.guide.operationsfunctions)。
例如，如果 `Op1` 、 `Op2` 和 `Op3` 全都是 `Qubit[] => Unit` 作業，但 `Op1` 支援、支援 `Adjoint` `Op2` `Controlled` 和 `Op3` 兩者都支援：
  * `[Op1, Op2]`是作業的陣列 `(Qubit[] => Unit)` 。
  * `[Op1, Op3]`是作業的陣列 `(Qubit[] => Unit is Adj)` 。
  * `[Op2, Op3]`是作業的陣列 `(Qubit[] => Unit is Ctl)` 。

不過，雖然作業 `(Qubit[] => Unit is Adj)` 和 `(Qubit[] => Unit is Ctl)` 具有的通用基底類型 `(Qubit[] => Unit)` ，但這些作業的*陣列*並不會共用通用基底類型。

例如， `[[Op1], [Op2]]` 目前會引發錯誤，因為它會嘗試建立兩個不相容陣列類型和的陣列 `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` 。

如需 callables 的詳細資訊，請參閱此頁面上的可呼叫[運算式](#callable-expressions)或[Q # 中的作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="conditional-expressions"></a>條件運算式

假設有兩個相同類型的運算式和一個布林運算式，請使用問號、和分隔號來形成條件運算式 `?` `|` 。 指定時 `a==b ? c | d` ， `c` 如果為 true，則條件運算式的值為，如果為 false，則為 `a==b` `d` 。

### <a name="conditional-expressions-with-callables"></a>具有 callables 的條件運算式

條件運算式可能會評估為具有相同輸入和輸出的作業，但支援不同的函子。 在此情況下，條件運算式的類型是具有輸入和輸出的作業，可支援這兩個運算式所支援的任何函子。
例如，如果、和都是，則支援、和支援 `Op1` `Op2` `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` 兩者：

- `flag ? Op1 | Op2`這是一種作業 `(Qubit[] => Unit)` 。
- `flag ? Op1 | Op3`這是一種作業 `(Qubit[] => Unit is Adj)` 。
- `flag ? Op2 | Op3`這是一種作業 `(Qubit[] => Unit is Ctl)` 。

如果兩個可能的結果運算式中有一個包含函式或作業呼叫，該呼叫只會在該結果是呼叫的值時才會發生。 例如，在案例中 `a==b ? C(qs) | D(qs)` ，如果 `a==b` 為 true，則會叫用作業 `C` ，如果是 false，則只 `D` 會叫用作業。 這個方法類似于其他語言的*簡短*運算。

## <a name="callable-expressions"></a>可呼叫的運算式

可呼叫的常值是在編譯範圍中定義的作業或函式的名稱。 例如， `X` 是參考標準程式庫作業的作業常值 `X` ，而 `Message` 是參考標準程式庫函數的函式常值 `Message` 。

如果作業支援 `Adjoint` 仿函數，則為作業 `Adjoint op` 運算式。
同樣地，如果作業支援 `Controlled` 仿函數，則 `Controlled op` 是作業運算式。
如需這些運算式類型的詳細資訊，請參閱[呼叫](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)作業特製化。

除了解除 `Adjoint` `Controlled` 包裝運算子和使用的陣列索引以外，函子（和）系結比其他所有運算子更緊密 `!` `[ ]` 。
因此，下列各項都是有效的，假設作業支援使用的函子：

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a>型別參數化可呼叫運算式

您可以使用可呼叫的常值做為值，例如，將它指派給變數，或將它傳遞給另一個可呼叫的。 在此情況下，如果可呼叫的[型別參數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)，您就必須提供參數做為可呼叫值的一部分。

可呼叫的值不能有任何未指定的類型參數。 例如，如果是具有簽章的函式 `Fun` `'T1->Unit` ：

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>可呼叫的調用運算式

假設有可呼叫的運算式（作業或函式）以及可呼叫的簽章之輸入類型的元組運算式，您可以將元組運算式附加至可呼叫的運算式，以形成*調用運算式*。
調用運算式的類型是可呼叫的簽章的輸出類型。

例如，如果是具有簽章的作業 `Op` `((Int, Qubit) => Double)` ， `Op(3, qubit1)` 就是類型的運算式 `Double` 。
同樣地，如果是具有簽章的 `Sin` 函數 `(Double -> Double)` ， `Sin(0.1)` 則是類型的運算式 `Double` 。
最後，如果是具有簽章的函式 `Builder` `(Int -> (Int -> Int))` ，則 `Builder(3)` 是從到的函數 `Int` `Int` 。

叫用可呼叫值運算式的結果時，需要一組額外的括弧括住可呼叫的運算式。
因此，若要叫 `Builder` 用從上一段呼叫的結果，正確的語法為：

```qsharp
(Builder(3))(2)
```

叫用[型別參數化](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)可呼叫時，您可以在可呼叫運算式之後的角括弧內指定實際的型別參數 `< >` 。
此動作通常不是必要的，因為 Q # 編譯器會推斷實際的類型。
不過，如果未指定型別參數化引數，[部分應用程式](xref:microsoft.quantum.guide.operationsfunctions#partial-application)*就*需要此參數。
將具有不同仿函數支援的作業傳遞給可呼叫的時，它也很有用。

例如，如果有簽章，且具有簽章，且具有簽章 `Func` `('T1, 'T2, 'T1) -> 'T2` ，則 `Op1` `Op2` 會 `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` 以 `Func` `Op1` 做為第一個引數來叫用， `Op2` 第二個是，而 `Op3` 第三個是：

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

類型規格是必要的，因為 `Op3` 和 `Op1` 具有不同的類型，因此編譯器會將此視為不明確的指定。


## <a name="operator-precedence"></a>運算子優先順序

* 除了之外，所有二元運算子都是右向關聯 `^` 。

* 以方括弧括住 `[ ]` 陣列切割和索引，並在任何運算子之前系結。

* 在 `Adjoint` `Controlled` 陣列索引後，但在其他所有運算子之前的函子和系結。

* 運算和函式呼叫的括弧也會系結在任何運算子之前，但是在陣列索引和函子之後。

依優先順序排列的 Q # 運算子，從最高到最低：

運算子 | Arity | 描述 | 運算元類型
---------|----------|---------|---------------
 句號`!` | 一元 (Unary) | 解除包裝 | 任何使用者定義型別
 `-`, `~~~`, `not` | 一元 (Unary) | 數值負數、位補數、邏輯否定 | `Int`、 `BigInt` 或 `Double` 為 `-` ， `Int` 或 `BigInt` `~~~` 代表 `Bool``not`
 `^` | Binary | 整數乘冪 | `Int`或 `BigInt` 作為基底， `Int` 代表指數
 `/`, `*`, `%` | Binary | 除法、乘法、integer 模數 | `Int`、 `BigInt` 或 `Double` 適用于 `/` 和 `*` ， `Int` 或 `BigInt` 為`%`
 `+`, `-` | Binary | 加法或字串和陣列串連，減法 | `Int`、 `BigInt` 或 `Double` ，此外 `String` 或任何的陣列類型`+`
 `<<<`, `>>>` | Binary | 左 shift、right shift | `Int` 或 `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | 小於、小於或等於、大於、大於、等於或相等的比較 | `Int`、 `BigInt` 或`Double`
 `==`, `!=` | Binary | 等於、不等於比較 | 任何基本類型
 `&&&` | Binary | 位元 AND | `Int` 或 `BigInt`
 `^^^` | Binary | 位元 XOR | `Int` 或 `BigInt`
 <code>\|\|\|</code> | Binary | 位元 OR | `Int` 或 `BigInt`
 `and` | Binary | 邏輯 AND | `Bool`
 `or` | Binary | 邏輯 OR | `Bool`
 `..` | Binary/三元 | Range 運算子 | `Int`
 `?` `|` | 三元 | 條件式 | `Bool`左側的
`w/` `<-` | 三元 | 複製和更新 | 請參閱[複製和更新運算式](#copy-and-update-expressions)

## <a name="next-steps"></a>後續步驟

現在您可以使用 Q # 中的運算式，請移至[q # 中的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式，以瞭解如何定義和呼叫作業和函數。
