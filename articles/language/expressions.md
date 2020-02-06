---
title: 運算式 |Microsoft Docs
description: 運算式
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 83fe697aa07a8ab28bd64437c8f5746bc5893b27
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036302"
---
# <a name="expressions"></a>運算式

## <a name="grouping"></a>分組

假設有任何運算式，以括弧括住的相同運算式就是相同類型的運算式。
例如，`(7)` 是 `Int` 運算式，`([1,2,3])` 是 `Int`s 陣列的運算式，而 `((1,2))` 是類型 `(Int, Int)`的運算式。

在[型別模型](xref:microsoft.quantum.language.type-model#tuple-types)中所描述的簡單值和單一元素元組的等價，會移除 `(6)` 與群組之間的不明確，並 `(6)` 為單一元素的元組。

## <a name="symbols"></a>符號

系結或指派給型別之值的符號名稱 `'T` 是 `'T`型別的運算式。
例如，如果符號 `count` 系結至 `5`的整數值，則 `count` 為整數運算式。

## <a name="numeric-expressions"></a>數值運算式

數值運算式是 `Int`、`BigInt`或 `Double`類型的運算式。
也就是說，它們可以是整數或浮點數。

問 # 中的 `Int` 常值與中C#的整數常值相同，不同之處在于不需要尾端的 "l" 或 "l" （或允許）。
分別支援十六進位和二進位整數和 "0x" 和 "0b" 前置詞。

Q # 中 `BigInt` 常值與 .NET 中的大整數位符串相同，結尾為 "l" 或 "L"。
十六進位大整數支援 "0x" 前置詞。
因此，以下是 `BigInt` 常值的所有有效用法：

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

在 Q # 中的 `Double` 常值與中C#的雙常值相同，不同之處在于不需要尾端的 "d" 或 "d" （或允許）。

假設有任何元素類型的陣列運算式，就可以使用 `Length` 內建函數來形成 `Int` 運算式，並以括弧括住的陣列運算式 `(` 和 `)`。
例如，如果 `a` 系結至陣列，則 `Length(a)` 為整數運算式。
如果 `b` 是整數陣列的陣列，則 `Int[][]`，則 `Length(b)` 是 `b`中的子陣列數目，而 `Length(b[1])` 是 `b`中第二個子陣列中的整數數目。

假設有兩個相同類型的數值運算式，則可以使用二元運算子 `+`、`-`、`*`和 `/` 來形成新的數值運算式。
新運算式的類型會與組成運算式的類型相同。

假設有兩個整數運算式，可以使用二元運算子 `^` （乘冪）來形成新的整數運算式。
同樣地，`^` 可以與兩個雙重運算式搭配使用，以形成新的 double 運算式。
最後，`^` 可以在左邊使用大整數，並在右邊加上一個整數來形成新的大整數運算式。
在此情況下，第二個參數必須符合32位;如果不是，則會引發執行階段錯誤。

假設有兩個整數或大整數運算式，可以使用 `%` （模數）、`&&&` （位 AND）、`|||` （位 OR）或 `^^^` （位 XOR）運算子來形成新的整數或大整數運算式。

假設左邊有整數或大整數運算式，而且右邊有整數運算式，則可以使用 `<<<` （算術左移位）或 `>>>` （算術右移位）運算子，來建立與左邊運算式具有相同類型的新運算式。

轉換作業的第二個參數（移位量）必須大於或等於零;負位移金額的行為未定義。
任何移位作業的移位量也必須符合32位;如果不是，則會引發執行階段錯誤。
如果要移位的數位是整數，則會將位移量 `mod 64`的值加以解讀。也就是說，1的位移和65的位移具有相同的效果。

對於整數和大整數值，移位是算術。
將負數值向左或右移位會產生負數。
也就是，將一個步驟向左或向右移位，與分別為乘法或除以2的方式完全相同。

整數除法和整數模數會遵循與負數相同的行為C#。
也就是說，`a % b` 一定會具有與 `a`相同的正負號，而且 `b * (a / b) + a % b` 一律會等於 `a`。
例如，

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 5 | 2 | 2 | 1
 5 | -2 | -2 | 1
 -5 | 2 | -2 | -1
 -5 | -2 | 2 | -1

大整數除法和模數的運作方式相同。

假設有任何數值運算式，可以使用 `-` 一元運算子來形成新的運算式。
新的運算式將與組成運算式的類型相同。

假設有任何整數或大整數運算式，則可以使用 `~~~` （位補數）一元運算子來形成相同類型的新運算式。

## <a name="boolean-expressions"></a>布林運算式

這兩個 `Bool` 常值是 `true` 和 `false`。

假設有兩個相同基本型別的運算式，就可以使用 `==` 和 `!=` 二元運算子來建立 `Bool` 運算式。
如果兩個運算式相等，則運算式會是 true，否則為 false。

可能不會比較使用者定義類型的值，只可以比較其未包裝的值。 例如，使用「解除包裝」運算子 `!` （在 [ [Q # 類型模型] 頁面](xref:microsoft.quantum.language.type-model#user-defined-types)中說明），

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

`Qubit` 值的相等比較是否為身分識別相等;也就是說，這兩個運算式是否會識別相同的 qubit。
這兩個 qubits 的狀態不會由這項比較進行比較、存取、測量或修改。

`Double` 值的相等比較可能會因為進位效果而誤導。
例如，`49.0 * (1.0/49.0) != 1.0`。

假設有兩個數值運算式，可以使用二元運算子 `>`、`<`、`>=`和 `<=` 來建立新的布林運算式，如果第一個運算式分別大於、小於、大於或等於或小於或等於第二個運算式，則會是 true。

假設有兩個布林運算式，`and` 和 `or` 二元運算子可以用來建立新的布林運算式，如果兩個運算式都是 true，則為 true。

假設有任何布林運算式，`not` 一元運算子可以用來建立新的布林運算式，如果組成運算式為 false，則為 true。

## <a name="string-expressions"></a>字串運算式

Q # 允許在 `fail` 語句和 `Log` standard 函數中使用字串。

Q # 中的字串可以是常值或字串插值。
字串常值類似于大部分語言中的簡單字串常值：以雙引號括住的 Unicode 字元序列，`"`。
在字串內，`\` 可以使用反斜線字元來將雙引號字元轉義，並插入新行做為 `\n`、以 `\r`傳回的回車，以及做為 `\t`的索引標籤。
例如：

```qsharp
"\"Hello world!\", she said.\n"
```

String 插補的 Q # 語法是C# 7.0 語法的子集;Q # 不支援逐字（多行）字串插值。
請參閱C#語法的[*字串插值*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)。

插補字串內的運算式遵循 Q # 語法，而C#不是語法。
任何有效的 Q # 運算式可能會出現在字串插值中。

## <a name="qubit-expressions"></a>Qubit 運算式

唯一的 `Qubit` 運算式是系結至 `Qubit` 陣列 `Qubit` 值或陣列元素的符號。
沒有 `Qubit` 常值。

## <a name="pauli-expressions"></a>Pauli 運算式

四個 `Pauli` 值 `PauliI`、`PauliX`、`PauliY`和 `PauliZ`都是有效的 `Pauli` 運算式。

除了這以外，唯一的 `Pauli` 運算式是系結至 `Pauli` 陣列 `Pauli` 值或陣列元素的符號。

## <a name="result-expressions"></a>結果運算式

`One` 和 `Zero`這兩個 `Result` 值都是有效的 `Result` 運算式。

除了這以外，唯一的 `Result` 運算式是系結至 `Result` 陣列 `Result` 值或陣列元素的符號。
特別要注意的是，`One` 與整數 `1`不同，而且兩者之間並沒有直接的轉換。
`Zero` 和 `0`也是如此。

## <a name="range-expressions"></a>範圍運算式

假設有任何三個 `Int` 運算式 `start`、`step`和 `stop`，`start .. step .. stop` 是一個範圍運算式，其第一個元素為 `start`、第二個元素為 `start+step`、第三個元素為 `start+step+step`等等，直到傳遞 `stop` 為止。
例如，如果 `step` 是正數且 `stop < start`，範圍可能會是空的。
如果 `start` 和 `stop` 之間的差異是 `step`的整數倍數，則範圍的最後一個元素會 `stop`。也就是，範圍包含在兩端。

假設有任何兩個 `Int` 運算式 `start` 和 `stop`，`start .. stop` 就是等於 `start .. 1 .. stop`的範圍運算式。
請注意，即使 `stop` 小於 `start`，隱含的 `step` 仍為 + 1;在這種情況下，範圍是空的。

一些範例範圍如下：

- `1..3` 為1、2、3的範圍。
- `2..2..5` 是2，4的範圍。
- `2..2..6` 為範圍2、4、6。
- `6..-2..2` 為6、4、2的範圍。
- `2..1` 是空的範圍。
- `2..6..7` 為範圍2。
- `2..2..1` 是空的範圍。
- `1..-1..2` 是空的範圍。

## <a name="callable-expressions"></a>可呼叫的運算式

可呼叫的常值是在編譯範圍中定義的作業或函式的名稱。
例如，`X` 是參考標準程式庫 `X` 作業的作業常值，而 `Message` 是參考標準程式庫 `Message` 函數的函式常值。

如果作業支援 `Adjoint` 仿函數，則 `Adjoint op` 是作業運算式。
同樣地，如果作業支援 `Controlled` 仿函數，則 `Controlled op` 是作業運算式。
這些運算式的類型是在[函子](xref:microsoft.quantum.language.type-model#functors)中指定。

函子（`Adjoint` 和 `Controlled`）系結比其他所有運算子更嚴格，但解除包裝運算子 `!` 和使用 `[]`的陣列索引。
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

例如，如果 `Fun` 是具有簽章 `'T1->Unit`的函數：

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a>可呼叫的調用運算式

假設可呼叫的（作業或函式）運算式，以及可呼叫的簽章之輸入類型的元組運算式，則可以將元組運算式附加至可呼叫的運算式，藉以形成調用運算式。
調用運算式的類型是可呼叫的簽章的輸出類型。

例如，如果 `Op` 是具有簽章 `((Int, Qubit) => Double)`的作業，則 `Op(3, qubit1)` 是 `Double`類型的運算式。
同樣地，如果 `Sin` 是具有簽章 `(Double -> Double)`的函數，則 `Sin(0.1)` 是 `Double`類型的運算式。
最後，如果 `Builder` 是具有簽章 `(Int -> (Int -> Int))`的函式，則 `Builder(3)` 是從到 Int 的函式。

叫用可呼叫值運算式的結果時，需要一組額外的括弧括住可呼叫的運算式。
因此，若要叫用從上一個段落呼叫 `Builder` 的結果，正確的語法為：

```qsharp
(Builder(3))(2)
```

叫用型別參數化可呼叫時，可以在角括弧內指定實際的型別參數 `<`，然後在可呼叫的運算式之後 `>`。
這通常是不必要的，因為 Q # 編譯器會推斷實際的類型。
如果未指定型別參數化引數，部分應用程式（如下所示）就需要此參數。
當將具有不同仿函數支援的作業傳遞至可呼叫的時，它有時也很有用。

例如，如果 `Func` 有簽章 `('T1, 'T2, 'T1) -> 'T2`，`Op1` 和 `Op2` 會有簽章 `(Qubit[] => Unit is Adj)`，而 `Op3` 具有簽章 `(Qubit[] => Unit)`，以 `Func` 做為第一個引數，`Op1` 做為第二個，然後 `Op2` 為第三個：`Op3`

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

類型規格是必要的，因為 `Op3` 和 `Op1` 具有不同的類型，因此編譯器會將此視為不明確的指定。

### <a name="partial-application"></a>部分應用程式

假設有可呼叫的運算式，就可以將引數的子集提供給可呼叫的，藉以建立新的可呼叫。
這稱為「_部分應用程式_」。

在 Q # 中，部分套用的可呼叫是藉由撰寫一般調用運算式來表示，但針對未指定的引數，則使用底線 `_`。
產生的可呼叫與基底可呼叫具有相同的結果型別，以及用於作業的相同特製化。
部分應用程式的輸入類型只是已移除指定引數的原始類型。

如果在建立部分應用程式時，將可變動的變數當做指定的引數傳遞，則會使用變數目前的值。
此後變更變數的值不會影響部分應用程式。

例如，如果 `Op` 具有類型 `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`：

- `Op(5,(_,_))` 具有類型 `(((Qubit,Qubit), Double) => Unit is Adj)`，因此 `Op(5,_)`。
- `Op(_,(_,1.0))` 具有類型 `((Int, (Qubit,Qubit)) => Unit is Adj)`。
- `Op(_,((q1,q2),_))` 具有類型 `((Int,Double) => Unit is Adj)`。
   請注意，我們已在此套用單一元組等價。

如果部分套用的可呼叫具有編譯器無法推斷的型別參數，則必須在調用網站上提供。
部分應用程式不能有任何未指定的類型參數。

例如，如果 `Op` 具有類型 `(('T1, Qubit, 'T1) => Unit : Adjoint)`：

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

元組常值是適當類型的元素運算式序列，並以逗號分隔，並以 `(` 和 `)`括住。
例如，`(1, One)` 是 `(Int, Result)` 運算式。

除了常值以外，唯一的元組運算式是系結至元組值的符號、元組陣列的陣列元素，以及傳回元組的可呼叫調用。

## <a name="user-defined-type-expressions"></a>使用者定義型別運算式

使用者自訂類型的常值是由類型名稱後面接著類型的基礎元組類型的元組常值所組成。
例如，如果 `IntPair` 是以 `(Int, Int)`為基礎的使用者定義型別，則 `IntPair(2,3)` 會是該型別的有效常值。

除了常值以外，使用者定義型別的唯一運算式是系結至該型別、該型別陣列的陣列元素，以及傳回該型別之可呼叫調用的符號。

## <a name="unwrap-expressions"></a>解除包裝運算式

在 Q # 中，解除包裝運算子是 `!`的尾端驚嘆號。
例如，如果 `IntPair` 是具有基礎類型 `(Int, Int)`的使用者定義型別，而 `s` 是值 `IntPair(2,3)`的變數，則 `s!` 會 `(2,3)`。

針對其他使用者定義型別所定義的使用者自訂類型。 解除包裝運算子可以重複;例如，`s!!` 表示 `s`的雙重解除包裝值。
因此，如果 `WrappedPair` 是具有基礎類型 `IntPair`的使用者定義型別，而 `t` 是值 `WrappedPair(IntPair(1,2))`的變數，則 `t!!` 會 `(1,2)`。

`!` 運算子的優先順序高於陣列索引和切割 `[]` 以外的其他所有運算子。
`!` 和 `[]` 系結 positionally;也就是說，`a[i]![3]` 應該讀取為 `((a[i])!)[3]`：接受 `a`的 `i`第個元素，將它解除包裝，然後取得未包裝值的第3個元素（必須是陣列）。

`!` 運算子的優先順序有一個可能不明顯的影響。
如果函式或作業傳回值，因而解除包裝，則函式或作業呼叫必須以括弧括住，讓引數元組系結至呼叫，而不是系結。
例如，

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a>陣列運算式

陣列常值是一系列的一或多個元素運算式，並以逗號分隔，並以 `[` 和 `]`括住。
所有元素都必須與相同的型別相容。

如果一般專案類型是作業或函式類型，所有元素都必須具有相同的輸入和輸出類型。
陣列的元素類型會支援所有元素所支援的任何函子。
例如，如果 `Op1`、`Op2`和 `Op3` 都是 `Qubit[] => Unit`的，但 `Op1` 支援 `Adjoint`，`Op2` 支援 `Controlled`，而 `Op3` 同時支援：

- `[Op1, Op2]` 是 `(Qubit[] => Unit)` 作業的陣列。
- `[Op1, Op3]` 是 `(Qubit[] => Unit is Adj)` 作業的陣列。
- `[Op2, Op3]` 是 `(Qubit[] => Unit is Ctl)` 作業的陣列。

不允許空的陣列常值（`[]`）。
相反地，使用 `new ★[0]`，其中 `★` 作為適合類型的預留位置，可讓建立所需長度為零的陣列。

假設有兩個相同類型的陣列，則可以使用 binary `+` 運算子來形成新陣列，這是兩個數組的串連。
例如，`[1,2,3] + [4,5,6]` 是 `[1,2,3,4,5,6]`。

### <a name="array-creation"></a>陣列建立

假設有一個型別和一個 `Int` 運算式，就可以使用 `new` 運算子來配置指定大小的新陣列。
例如，`new Int[i+1]` 會配置具有 `i+1` 元素的新 `Int` 陣列。

新陣列的元素會初始化為與類型相關的預設值。
在大部分情況下，這會是零的部分變化。

對於實體參考的 qubits 和 callables 而言，沒有合理的預設值。
因此，對於這些類型，預設值為不正確參考，無法使用而不會造成執行階段錯誤。
這類似于C#或 JAVA 等語言中的 null 參考。
包含 qubits 或 callables 的陣列必須使用非預設值正確地初始化，才可以安全地使用它們的元素。 您可以在 <xref:microsoft.quantum.arrays>中找到適當的初始化常式。

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

假設有陣列運算式和 `Range` 運算式，則可以使用 `[` 和 `]` 陣列配量運算子來形成新的運算式。
新的運算式會與陣列具有相同的類型，而且會包含依 `Range`所定義的順序，以 `Range`的元素編制索引的陣列專案。
例如，如果 `a` 系結至 `Double`s 的陣列，則 `a[3..-1..0]` 是 `Double[]` 運算式，其中包含 `a` 的前四個元素，但順序與 `a`中出現的相反。

如果 `Range` 是空的，則產生的陣列配量會是長度為零的。

如果陣列運算式不是簡單的識別碼，則必須將它括在括弧內，才能進行配量。
例如，如果 `a` 和 `b` 都是 `Int`的陣列，則串連中的配量會表示為：

```qsharp
(a+b)[1..2..7]
```

Q # 中的所有陣列都是以零為基底。
也就是說，陣列 `a` 的第一個元素一律會 `a[0]`。

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

假設有陣列運算式和 `Int` 運算式，則可以使用 `[` 和 `]` 陣列元素運算子來形成新的運算式。
新的運算式將與陣列的元素類型相同。
例如，如果 `a` 系結至 `Double`s 的陣列，則 `a[4]` 是 `Double` 運算式。

如果陣列運算式不是簡單的識別碼，則必須將它括在括弧內，才能選取元素。
例如，如果 `a` 和 `b` 都是 `Int`的陣列，則串連中的元素會表示為：

```qsharp
(a+b)[13]
```

Q # 中的所有陣列都是以零為基底。
也就是說，陣列 `a` 的第一個元素一律會 `a[0]`。


## <a name="copy-and-update-expressions"></a>複製和更新運算式

您可以透過複製和更新運算式，從現有的陣列建立新的陣列。
複製和更新運算式是格式為 `expression1 w/ expression2 <- expression3`的運算式，其中 `expression1` 必須是某些類型 `T`的類型 `T[]`。 第二個 `expression2` 會定義相較于 `expression1` 中的陣列，要修改之元素的索引，而且必須是 `Int` 類型或 `Range`類型的類型。 如果 `expression2` 的類型為 `Int`，`expression3` 必須是 `T`類型。 如果 `expression2` 的類型為 `Range`，`expression3` 必須是 `T[]`類型。

「複製並更新」運算式 `arr w/ idx <- value` 會在 `arr`中，以所有設定為對應元素的專案來建立新的陣列，但 `idx`的元素除外，其設定為 `value`中的一個專案。 例如，如果 `arr` 包含 `[0,1,2,3]`的陣列，則 
- `arr w/ 0 <- 10` 是陣列 `[10,1,2,3]`。
- `arr w/ 2 <- 10` 是陣列 `[0,1,10,3]`。
- `arr w/ 0..2..3 <- [10,12]` 是陣列 `[10,1,12,3]`。

使用者定義類型中的命名專案有類似的運算式。 請考慮類型的範例 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
如果 `c` 包含 `Complex(1.,-1.)`類型的值，則 `c w/ Re <- 0.` 是評估為 `Complex(0.,-1.)`之類型 `Complex` 的運算式。

## <a name="conditional-expressions"></a>條件運算式

假設有兩個相同類型和布林運算式的其他運算式，則可以使用問號 `?` 和分隔號 `|`來形成條件運算式。
例如，`a==b ? c | d`。
在此範例中，如果 `a==b` 為 true，則會 `c` 條件運算式的值，而如果為 false，則 `d`。

這兩個運算式可能會評估為具有相同輸入和輸出但支援不同函子的作業。
在此情況下，條件運算式的類型是具有這些輸入和輸出的作業，可支援這兩個運算式所支援的任何函子。
例如，如果 `Op1`、`Op2`和 `Op3` 都是 `Qubit[]=>Unit`的，但 `Op1` 支援 `Adjoint`，`Op2` 支援 `Controlled`，而 `Op3` 同時支援：

- `flag ? Op1 | Op2` 是 `(Qubit[] => Unit)` 作業。
- `flag ? Op1 | Op3` 是 `(Qubit[] => Unit is Adj)` 作業。
- `flag ? Op2 | Op3` 是 `(Qubit[] => Unit is Ctl)` 作業。

如果兩個可能的結果運算式中有一個包含函式或作業呼叫，只有當該結果是將成為呼叫值的呼叫時，才會進行該呼叫。
例如，在案例中 `a==b ? C(qs) | D(qs)`，如果 `a==b` 為 true，則會叫用 `C` 作業，如果是 false，則只會叫用 `D`。
這類似于其他語言的簡短運算。


## <a name="operator-precedence"></a>運算子優先順序

除了 `^`以外，所有二元運算子都是右向關聯。

括弧、`[` 和 `]`，針對陣列切割和索引編制，請在任何運算子之前系結。

函子在陣列索引之後，但在其他所有運算子之前，會 `Adjoint` 和 `Controlled` 系結。

運算和函式呼叫的括弧也會系結在任何運算子之前，但是在陣列索引和函子之後。

依優先順序排列的運算子，從最高到最低：

運算子 | Arity | 描述 | 運算元類型
---------|----------|---------|---------------
 尾端 `!` | 一元 (Unary) | 解除包裝 | 任何使用者定義型別
 `-`、`~~~`、`not` | 一元 (Unary) | 數值負數、位補數、邏輯否定 | `Int`、`BigInt` 或 `Double` `-`、`Int` 或 `BigInt` `~~~`、`Bool``not`
 `^` | Binary | 整數乘冪 | `Int` 或 `BigInt` 作為基底，`Int` 指數
 `/`、`*`、`%` | Binary | 除法、乘法、integer 模數 | `Int`、`BigInt` 或 `Double` `/` 和 `*`、`Int` 或 `BigInt` `%`
 `+`, `-` | Binary | 加法或字串和陣列串連，減法 | `Int`、`BigInt` 或 `Double`，此外 `String` 或任何 `+` 的陣列類型
 `<<<`, `>>>` | Binary | 左 shift、right shift | `Int` 或 `BigInt`
 `<`, `<=`, `>`, `>=` | Binary | 小於、小於或等於、大於、大於、等於或相等的比較 | `Int`、`BigInt` 或 `Double`
 `==`, `!=` | Binary | 等於、不等於比較 | 任何基本類型
 `&&&` | Binary | 位元 AND | `Int` 或 `BigInt`
 `^^^` | Binary | 位元 XOR | `Int` 或 `BigInt`
 <code>\|\|\|</code> | Binary | 位元 OR | `Int` 或 `BigInt`
 `and` | Binary | 邏輯 AND | `Bool`
 `or` | Binary | 邏輯 OR | `Bool`
 `..` | Binary/三元 | Range 運算子 | `Int`
 `?` `|` | 三元 | 條件式 | 左側的 `Bool`
`w/` `<-` | 三元 | 複製和更新 | 請參閱[複製和更新運算式](#copy-and-update-expressions)
