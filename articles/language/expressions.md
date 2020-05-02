---
title: 'Q # 運算式'
description: '瞭解如何指定、參考和合併常數、變數、運算子、作業和函數，做為 Q # 中的運算式。'
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683916"
---
# <a name="expressions"></a>運算式

## <a name="grouping"></a>分組

假設有任何運算式，以括弧括住的相同運算式就是相同類型的運算式。
`(7)`例如， `Int`是運算式， `([1,2,3])`是 s 類型的`Int`運算式，而`((1,2))`是型別為的運算式。 `(Int, Int)`

在[型別模型](xref:microsoft.quantum.language.type-model#tuple-types)中所描述的簡單值和單一元素元組之間的等價， `(6)`會移除做為`(6)`群組和單一元素元組之間的多義性。

## <a name="symbols"></a>Symbols

系結或指派給類型`'T`值的符號名稱是類型`'T`的運算式。
例如，如果符號`count`系結至整數值`5`，則`count`為整數運算式。

## <a name="numeric-expressions"></a>數值運算式

數值運算式是、 `Int` `BigInt`或`Double`類型的運算式。
也就是說，它們可以是整數或浮點數。

`Int`Q # 中的常值與 c # 中的整數常值相同，不同之處在于不需要尾端 "l" 或 "L" （或允許）。
分別支援十六進位和二進位整數和 "0x" 和 "0b" 前置詞。

`BigInt`Q # 中的常值與 .NET 中的大整數位符串相同，結尾為 "l" 或 "L"。
十六進位大整數支援 "0x" 前置詞。
因此，下列是`BigInt`常值的所有有效用法：

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

`Double`Q # 中的常值與 c # 中的雙常值相同，不同之處在于不需要尾端的 "d" 或 "D" （或允許）。

假設有任何元素類型的陣列運算式，則`Int`可以使用內`Length`建函數來形成運算式， `(`並以括弧括住陣列運算式和。 `)`
例如，如果`a`系結至陣列，則`Length(a)`為整數運算式。
如果`b`是`Int[][]`整數陣列的陣列， `Length(b)`則是中`b`的子陣列數目，而`Length(b[1])`是中第二個子陣列中的整數數目。 `b`

假設有兩個相同類型的數值運算式，則可以`+`使用`-`二元`*`運算子、 `/` 、和來形成新的數值運算式。
新運算式的類型會與組成運算式的類型相同。

假設有兩個整數運算式，可以`^`使用二元運算子（乘冪）來形成新的整數運算式。
同樣地`^` ，可以搭配兩個雙重運算式使用，以形成新的 double 運算式。
最後， `^`可以搭配左邊的大整數和右邊的整數來形成新的大整數運算式。
在此情況下，第二個參數必須符合32位;如果不是，則會引發執行階段錯誤。

假設有兩個整數或大整數運算式，則可以`%`使用（模數）、 `&&&` （位 and）、 `|||` （位 or）或`^^^` （位 XOR）運算子來形成新的整數或大整數運算式。

指定左邊的整數或大整數運算式，以及右邊的整數運算式時，可以使用`<<<` （算術左移位）或`>>>` （算術右移位）運算子，來建立與左邊運算式具有相同類型的新運算式。

轉換作業的第二個參數（移位量）必須大於或等於零;負位移金額的行為未定義。
任何移位作業的移位量也必須符合32位;如果不是，則會引發執行階段錯誤。
如果要移動的數位是整數，則會解讀`mod 64`移位量;也就是說，1的位移和65的位移具有相同的效果。

對於整數和大整數值，移位是算術。
將負數值向左或右移位會產生負數。
也就是，將一個步驟向左或向右移位，與分別為乘法或除以2的方式完全相同。

整數除法和整數模數會遵循與 c # 相同的負數行為。
也就是`a % b` ，一律會有相同的正負`a`號， `b * (a / b) + a % b`而且一定會`a`相等。
例如：

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

大整數除法和模數的運作方式相同。

假設有任何數值運算式，可能會使用`-`一元運算子來形成新的運算式。
新的運算式將與組成運算式的類型相同。

假設有任何整數或大整數運算式，則可以使用`~~~` （位補數）一元運算子來形成相同類型的新運算式。

## <a name="boolean-expressions"></a>布林運算式

這兩`Bool`個常值`true`為`false`和。

假設有兩個相同基本類型的運算式，則`==`和`!=`二元運算子可用來建立`Bool`運算式。
如果兩個運算式相等，則運算式會是 true，否則為 false。

可能不會比較使用者定義類型的值，只可以比較其未包裝的值。 例如，使用「解除包裝」運算子`!` （說明于 [ [Q # 類型模型] 頁面](xref:microsoft.quantum.language.type-model#user-defined-types)中），

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

`Qubit`值的相等比較是識別相等的;也就是說，這兩個運算式是否會識別相同的 qubit。
這兩個 qubits 的狀態不會由這項比較進行比較、存取、測量或修改。

值的`Double`相等比較可能會因為進位效果而誤導。
例如， `49.0 * (1.0/49.0) != 1.0`。

假設有兩個數值運算式，如果第`>`一個`<`運算式`>=`分別大於`<=` 、小於、大於或等於或小於或等於第二個運算式，則二元運算子、、和可能會用來建立新的布林值運算式。

假設有兩個布林運算式， `and`和`or`二元運算子可用來建立新的布林運算式，如果這兩個運算式（resp）都是 true，則為 true。

假設有任何布林運算式， `not`一元運算子可用來建立新的布林運算式，如果組成運算式為 false，則為 true。

## <a name="string-expressions"></a>字串運算式

Q # 允許在`fail`語句和`Log`標準函數中使用字串。

Q # 中的字串可以是常值或字串插值。
字串常值類似于大部分語言中的簡單字串常值：以雙引號括住的 Unicode 字元序列`"`。
在字串內，反斜線`\`字元可用來將雙引號字元轉義，並插入新行做為`\n`、做為`\r`的回車，以及做為`\t`索引標籤。
例如：

```qsharp
"\"Hello world!\", she said.\n"
```

String 插補的 Q # 語法是 c # 7.0 語法的子集;Q # 不支援逐字（多行）字串插值。
請參閱 c # 語法的[*字串插值*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。

插補字串內的運算式遵循 Q # 語法，而不是 c # 語法。
任何有效的 Q # 運算式可能會出現在字串插值中。

## <a name="qubit-expressions"></a>Qubit 運算式

唯一`Qubit`的運算式是系結至`Qubit`陣列的值或陣列元素的`Qubit`符號。
沒有任何`Qubit`常值。

## <a name="pauli-expressions"></a>Pauli 運算式

、、 `Pauli`和`PauliZ`這`PauliI`四`PauliX`個`PauliY`值都是有效`Pauli`的運算式。

除了這以外，唯一`Pauli`的運算式是系結至`Pauli`陣列值或陣列元素的`Pauli`符號。

## <a name="result-expressions"></a>結果運算式

`One`和`Zero`這`Result`兩個值都是有效`Result`的運算式。

除了這以外，唯一`Result`的運算式是系結至`Result`陣列值或陣列元素的`Result`符號。
特別要注意的`One`是，與整數`1`不相同，而且它們之間沒有直接的轉換。
`Zero`和`0`的情況也是如此。

## <a name="range-expressions"></a>範圍運算式

假設有任何`Int`三`start`個`step`運算式、 `stop`和`start .. step .. stop` ，就是一個範圍運算式，其`start`第一個元素是`start+step`、第二個`start+step+step`元素是、第三`stop`個元素，依此類推，直到傳遞為止。
例如， `step`如果是正數和`stop < start`，範圍可能會是空的。
如果`stop`和之間`start`的差異是的`stop` `step`整數倍數，則範圍的最後一個元素會是。也就是，範圍包含在兩端。

假設有兩`Int`個`start`運算式`stop`和`start .. stop` ，是等於的範圍運算式`start .. 1 .. stop`。
請注意，即使`step` `stop`小於，隱含也是 + 1 `start`;在這種情況下，範圍是空的。

一些範例範圍如下：

- `1..3`為1、2、3的範圍。
- `2..2..5`是範圍2，4。
- `2..2..6`為範圍2、4、6。
- `6..-2..2`為6、4、2的範圍。
- `2..1`這是空的範圍。
- `2..6..7`為範圍2。
- `2..2..1`這是空的範圍。
- `1..-1..2`這是空的範圍。

## <a name="callable-expressions"></a>可呼叫的運算式

可呼叫的常值是在編譯範圍中定義的作業或函式的名稱。
例如， `X`是參考標準程式庫`X`作業的作業常值，而`Message`是參考標準程式庫`Message`函數的函式常值。

如果作業支援`Adjoint`仿函數，則`Adjoint op`為作業運算式。
同樣地，如果作業支援`Controlled`仿函數，則`Controlled op`是作業運算式。
這些運算式的類型是在[函子](xref:microsoft.quantum.language.type-model#functors)中指定。

除了解除`Adjoint`包裝`Controlled`運算子`!`和使用`[]`的陣列索引以外，函子（和）系結比其他所有運算子更緊密。
因此，假設作業支援使用的函子，則下列各項都是合法的：

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

可呼叫的常值可用來做為值，比方說，是指派給變數或傳遞給另一個可呼叫的。
在此情況下，如果可呼叫的型別參數為，則必須將它們提供作為可呼叫值的一部分。
可呼叫的值不能有任何未指定的類型參數。

例如，如果`Fun`是具有簽章的函`'T1->Unit`式：

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>可呼叫的調用運算式

假設可呼叫的（作業或函式）運算式，以及可呼叫的簽章之輸入類型的元組運算式，則可以將元組運算式附加至可呼叫的運算式，藉以形成調用運算式。
調用運算式的類型是可呼叫的簽章的輸出類型。

例如，如果`Op`是具有簽章的作業`((Int, Qubit) => Double)`， `Op(3, qubit1)`就是類型`Double`的運算式。
同樣地， `Sin`如果是具有簽章`(Double -> Double)`的`Sin(0.1)`函數，則是類型`Double`的運算式。
最後，如果`Builder`是具有簽章的`(Int -> (Int -> Int))`函式`Builder(3)` ，則是從到 Int 的函式。

叫用可呼叫值運算式的結果時，需要一組額外的括弧括住可呼叫的運算式。
因此，若要叫用從上`Builder`一段呼叫的結果，正確的語法為：

```qsharp
(Builder(3))(2)
```

叫用型別參數化可呼叫時，可以在角括弧`<`內以及`>`可呼叫運算式之後指定實際的型別參數。
這通常是不必要的，因為 Q # 編譯器會推斷實際的類型。
如果未指定型別參數化引數，部分應用程式（如下所示）就需要此參數。
當將具有不同仿函數支援的作業傳遞至可呼叫的時，它有時也很有用。

例如，如果`Func` `('T1, 'T2, 'T1) -> 'T2`有簽章， `Op1`且`Op2`具有簽`(Qubit[] => Unit is Adj)`章， `Op3`且具有`(Qubit[] => Unit)`簽章， `Func`則`Op1`會以做為第`Op2`一個引數來叫`Op3`用，第二個是，而當做第三個：

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

類型規格是必要的， `Op3`因為`Op1`和具有不同的類型，因此編譯器會將此視為不明確的指定。

### <a name="partial-application"></a>部分應用程式

假設有可呼叫的運算式，就可以將引數的子集提供給可呼叫的，藉以建立新的可呼叫。
這稱為「_部分應用程式_」。

在 Q # 中，部分套用的可呼叫是藉由撰寫一般調用運算式來表示，但針對`_`未指定的引數，則使用底線。
產生的可呼叫與基底可呼叫具有相同的結果型別，以及用於作業的相同特製化。
部分應用程式的輸入類型只是已移除指定引數的原始類型。

如果在建立部分應用程式時，將可變動的變數當做指定的引數傳遞，則會使用變數目前的值。
此後變更變數的值不會影響部分應用程式。

例如，如果`Op`的類型`((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`為：

- `Op(5,(_,_))`具有類型`(((Qubit,Qubit), Double) => Unit is Adj)`，因此為`Op(5,_)`。
- `Op(_,(_,1.0))` 的型別為 `((Int, (Qubit,Qubit)) => Unit is Adj)`。
- `Op(_,((q1,q2),_))` 的型別為 `((Int,Double) => Unit is Adj)`。
   請注意，我們已在此套用單一元組等價。

如果部分套用的可呼叫具有編譯器無法推斷的型別參數，則必須在調用網站上提供。
部分應用程式不能有任何未指定的類型參數。

例如，如果`Op`的類型`(('T1, Qubit, 'T1) => Unit : Adjoint)`為：

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a>遞迴

Q # callables 允許直接或間接遞迴。
也就是說，作業或函式可能會呼叫本身，或呼叫可直接或間接呼叫可呼叫作業的其他調用。

使用遞迴有兩個重要的批註，不過：

- 在作業中使用遞迴可能會干擾特定的優化。
  這可能會對演算法的執行時間產生重大影響。
- 在實際的量子裝置上執行時，堆疊空間可能會受到限制，因此深度遞迴可能會導致執行階段錯誤。
  特別是，Q # 編譯器和執行時間不會識別並優化尾遞迴。

## <a name="tuple-expressions"></a>元組運算式

元組常值是適當類型的元素運算式序列，以逗號分隔，並包含在和`(` `)`中。
例如， `(1, One)`是`(Int, Result)`運算式。

除了常值以外，唯一的元組運算式是系結至元組值的符號、元組陣列的陣列元素，以及傳回元組的可呼叫調用。

## <a name="user-defined-type-expressions"></a>使用者定義型別運算式

使用者自訂類型的常值是由類型名稱後面接著類型的基礎元組類型的元組常值所組成。
例如，如果`IntPair`是以為基礎的使用者定義型別`(Int, Int)`，則`IntPair(2,3)`會是該型別的有效常值。

除了常值以外，使用者定義型別的唯一運算式是系結至該型別、該型別陣列的陣列元素，以及傳回該型別之可呼叫調用的符號。

## <a name="unwrap-expressions"></a>解除包裝運算式

在 Q # 中，解除包裝運算子是尾端驚嘆號`!`。
例如`IntPair` ，如果是具有基礎類型`(Int, Int)`的使用者定義型別，而`s`是具有值`IntPair(2,3)`的變數，則`s!`會是。 `(2,3)`

針對其他使用者定義型別所定義的使用者自訂類型。 解除包裝運算子可以重複;例如， `s!!`表示的雙重解除包裝值`s`。
因此，如果`WrappedPair`是具有基礎類型`IntPair`的使用者定義型別，而`t`是具有值`WrappedPair(IntPair(1,2))`的變數，則`t!!`會是`(1,2)`。

除了`!`陣列索引和切割以外，運算子的優先順序高於`[]`其他所有運算子。
`!`和`[]`系結 positionally;也就是`a[i]![3]` ，您應該將`((a[i])!)[3]`它視為： `i`取得的 ' th `a`' 元素，將它解除包裝，然後取得未包裝值的第3個元素（必須是陣列）。

`!`運算子的優先順序有一個可能不明顯的影響。
如果函式或作業傳回值，因而解除包裝，則函式或作業呼叫必須以括弧括住，讓引數元組系結至呼叫，而不是系結。
例如：

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>陣列運算式

陣列常值是一系列的一或多個元素運算式，並以逗號分隔， `[`並`]`包含在和中。
所有元素都必須與相同的型別相容。

如果一般專案類型是作業或函式類型，所有元素都必須具有相同的輸入和輸出類型。
陣列的元素類型會支援所有元素所支援的任何函子。
`Op1`例如，如果、 `Op2`和`Op3`都是`Qubit[] => Unit`， `Op1` `Adjoint` `Op2` `Controlled` `Op3`則支援、和支援兩者：

- `[Op1, Op2]`是`(Qubit[] => Unit)`作業的陣列。
- `[Op1, Op3]`是`(Qubit[] => Unit is Adj)`作業的陣列。
- `[Op2, Op3]`是`(Qubit[] => Unit is Ctl)`作業的陣列。

不允許空的`[]`陣列常值。
相反地`new ★[0]`，使用`★` ，其中是適合類型的預留位置，可讓建立所需長度為零的陣列。

假設有兩個相同類型的陣列，則`+`可以使用二元運算子來形成新陣列，這是兩個數組的串連。
例如， `[1,2,3] + [4,5,6]`是`[1,2,3,4,5,6]`。

### <a name="array-creation"></a>陣列建立

假設有型別和`Int`運算式， `new`運算子可用來配置指定大小的新陣列。
例如， `new Int[i+1]`會使用`Int` `i+1`元素配置新的陣列。

新陣列的元素會初始化為與類型相關的預設值。
在大部分情況下，這會是零的部分變化。

對於實體參考的 qubits 和 callables 而言，沒有合理的預設值。
因此，對於這些類型，預設值為不正確參考，無法使用而不會造成執行階段錯誤。
這類似于 c # 或 JAVA 等語言中的 null 參考。
包含 qubits 或 callables 的陣列必須使用非預設值正確地初始化，才可以安全地使用它們的元素。 您可以在中找到適當的<xref:microsoft.quantum.arrays>初始化常式。

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

元組類型會依元素初始化。


### <a name="jagged-arrays"></a>不規則陣列

不規則陣列（有時稱為「陣列陣列」）是其元素為數組的陣列。 不規則陣列的元素可以是不同的大小。 下列範例顯示如何宣告和初始化代表乘法資料表的不規則陣列。

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


### <a name="array-slices"></a>陣列配量

假設有陣列運算式和`Range`運算式，則可以使用`[`和`]`陣列配量運算子來形成新的運算式。
新的運算式會與陣列具有相同的類型，而且會包含由的專案所編制索引的陣列專案`Range`（依照所定義的順序） `Range`。
例如， `a`如果系結至的陣列`Double`，則`a[3..-1..0]`是包含前四個`Double[]`專案的`a`運算式，但在中出現的順序則相反`a`。

如果`Range`是空的，則產生的陣列配量會是長度為零的。

如果陣列運算式不是簡單的識別碼，則必須將它括在括弧內，才能進行配量。
比方說，如果`a`和`b`都是 s 的`Int`陣列，則串連中的配量會表示為：

```qsharp
(a+b)[1..2..7]
```

Q # 中的所有陣列都是以零為基底。
也就是說，陣列`a`的第一個元素一定`a[0]`是。

從0.8 版開始，我們支援範圍切割的內容相關運算式。 特別的是，範圍的開始和結束值可能會在範圍切割運算式的內容中省略。 在這種情況下，編譯器將會套用下列規則，以推斷範圍的預期分隔符號。 

例如，如果省略範圍起始值，則推斷的起始值 
- 如果未指定任何步驟，或指定的步驟是正數，則為零，而 
- 如果指定的步驟是負數，則為已切割陣列的長度減一。 

如果省略範圍結束值，則推斷的結束值 
- 這是已切割陣列的長度減一，如果未指定任何步驟，或指定的步驟是正數，則為， 
- 如果指定的步驟是負數，則為零。 

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

## <a name="array-element-expressions"></a>陣列元素運算式

假設有陣列運算式和`Int`運算式，則可以使用`[`和`]`陣列元素運算子來形成新的運算式。
新的運算式將與陣列的元素類型相同。
`a`例如，如果系結至的`Double`陣列，則`a[4]`為`Double`運算式。

如果陣列運算式不是簡單的識別碼，則必須將它括在括弧內，才能選取元素。
比方說，如果`a`和`b`都是 s 的`Int`陣列，則串連中的元素會表示為：

```qsharp
(a+b)[13]
```

Q # 中的所有陣列都是以零為基底。
也就是說，陣列`a`的第一個元素一定`a[0]`是。


## <a name="copy-and-update-expressions"></a>複製和更新運算式

您可以透過複製和更新運算式，從現有的陣列建立新的陣列。
複製和更新運算式是`expression1 w/ expression2 <- expression3`格式的運算式，其中`expression1`必須是某種類型`T[]` `T`的類型。 第二`expression2`個定義要修改之元素的索引（相較于中`expression1`的陣列），而且必須是類型的類型`Int`或。 `Range` 如果`expression2`的型`Int`別為`expression3` ，則必須是型`T`別。 如果`expression2`的型`Range`別為`expression3` ，則必須是型`T[]`別。

「複製並更新」 `arr w/ idx <- value`運算式會建立新的陣列，其中所有專案都設定為中`arr`的對應專案，但的元素除外`idx`，其設定為中`value`的一個。 例如，如果`arr`包含陣列`[0,1,2,3]`，則 
- `arr w/ 0 <- 10`是陣列`[10,1,2,3]`。
- `arr w/ 2 <- 10`是陣列`[0,1,10,3]`。
- `arr w/ 0..2..3 <- [10,12]`是陣列`[10,1,12,3]`。

使用者定義類型中的命名專案有類似的運算式。 請考慮類型的範例 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
如果`c`包含型`Complex(1.,-1.)`別的值，則`c w/ Re <- 0.`為評估為`Complex` `Complex(0.,-1.)`之型別的運算式。

## <a name="conditional-expressions"></a>條件運算式

假設有兩個相同類型和布林運算式的其他運算式，則可以使用問號`?`和分隔號來形成條件運算式。 `|`
例如， `a==b ? c | d`。
在此範例中，條件運算式的值會是， `c`如果`a==b`為 true， `d`則為，如果為 false，則為。

這兩個運算式可能會評估為具有相同輸入和輸出但支援不同函子的作業。
在此情況下，條件運算式的類型是具有這些輸入和輸出的作業，可支援這兩個運算式所支援的任何函子。
`Op1`例如，如果、 `Op2`和`Op3`都是`Qubit[]=>Unit`， `Op1` `Adjoint` `Op2` `Controlled` `Op3`則支援、和支援兩者：

- `flag ? Op1 | Op2`這是`(Qubit[] => Unit)`一種作業。
- `flag ? Op1 | Op3`這是`(Qubit[] => Unit is Adj)`一種作業。
- `flag ? Op2 | Op3`這是`(Qubit[] => Unit is Ctl)`一種作業。

如果兩個可能的結果運算式中有一個包含函式或作業呼叫，只有當該結果是將成為呼叫值的呼叫時，才會進行該呼叫。
例如`a==b ? C(qs) | D(qs)`，在案例中，如果`a==b`為 true `C` ，則會叫用作業，如果它是 false，則只`D`會叫用。
這類似于其他語言的簡短運算。


## <a name="operator-precedence"></a>運算子優先順序

除了之外，所有二元運算子都是右向`^`關聯。

如果是`[`陣列`]`切割和編制索引，請在任何運算子之前系結，並以方括弧括住。

在陣列`Adjoint`索引`Controlled`後，但在其他所有運算子之前的函子和系結。

運算和函式呼叫的括弧也會系結在任何運算子之前，但是在陣列索引和函子之後。

依優先順序排列的運算子，從最高到最低：

運算子 | Arity | 描述 | 運算元類型
---------|----------|---------|---------------
 句號`!` | 一元 (Unary) | 解除包裝 | 任何使用者定義型別
 `-`, `~~~`, `not` | 一元 (Unary) | 數值負數、位補數、邏輯否定 | `Int`、 `BigInt`或`Double`為`-`， `Int`或`BigInt` `~~~`代表`Bool``not`
 `^` | Binary | 整數乘冪 | `Int`或`BigInt`作為基底， `Int`代表指數
 `/`, `*`, `%` | Binary | 除法、乘法、integer 模數 | `Int`、 `BigInt`或`Double`適用`/`于`*`和`Int` ， `BigInt`或為`%`
 `+`, `-` | Binary | 加法或字串和陣列串連，減法 | `Int`、 `BigInt`或`Double`，此外`String`或任何的陣列類型`+`
 `<<<`, `>>>` | Binary | 左 shift、right shift | `Int` 或 `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | 小於、小於或等於、大於、大於、等於或相等的比較 | `Int`、 `BigInt`或`Double`
 `==`, `!=` | Binary | 等於、不等於比較 | 任何基本類型
 `&&&` | Binary | 位元 AND | `Int` 或 `BigInt`
 `^^^` | Binary | 位元 XOR | `Int` 或 `BigInt`
 <code>\|\|\|</code> | Binary | 位元 OR | `Int` 或 `BigInt`
 `and` | Binary | 邏輯 AND | `Bool`
 `or` | Binary | 邏輯 OR | `Bool`
 `..` | Binary/三元 | Range 運算子 | `Int`
 `?` `|` | 三元 | 條件式 | `Bool`左側的
`w/` `<-` | 三元 | 複製和更新 | 請參閱[複製和更新運算式](#copy-and-update-expressions)
