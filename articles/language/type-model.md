---
title: '問 # 型別模型 |Microsoft Docs'
description: Q# 類型模型
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 0aabb144779da301b71ad215c8e975cc29b4dcce
ms.sourcegitcommit: ca5015fed409eaf0395a89c2e4bc6a890c360aa2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76871629"
---
# <a name="the-type-model"></a>型別模型

本節會配置 Q # 類型模型，並描述用於指定和使用類型的語法。
我們注意到，Q # 是*強型*別語言，因此小心使用這些型別可協助編譯器在編譯時期提供有關 Q # 程式的強式保證。

為了提供最強的保證，在 Q # 中類型之間的轉換必須使用表達該轉換的函式呼叫來明確地進行。 <xref:microsoft.quantum.convert> 命名空間中提供了各種不同的函數。
另一方面，Upcasts 到相容的型別就會隱含地發生。 

Q # 同時提供兩種基本類型，可以直接使用，以及從其他類型產生新類型的各種方式。
我們會在本節的其餘部分說明每個。

## <a name="primitive-types"></a>基本類型

Q # 語言提供了數種*基本類型*，可從中建造其他類型：

- `Int` 類型代表64位帶正負號的整數，例如： `2`、`107`、`-5`。
- `BigInt` 類型代表任意大小的帶正負號整數，例如 `2L`、`107L`、`-5L`。
   此類型是以 .NET 為基礎 <xref:System.Numerics.BigInteger>
   型.
- `Double` 類型代表雙精確度浮點數，例如： `0.0`、`-1.3`、`4e-7`。
- `Bool` 類型代表可 `true` 或 `false`的布林值。
- `Qubit` 類型代表量子位或 qubit。
   對使用者而言，`Qubit`是不透明的;除了將它們傳遞至另一個作業以外，唯一可行的作業是測試身分識別（相等）。
   最後，`Qubit`上的動作是藉由呼叫量子處理器上的內建指示來執行（或模擬）。
- `Pauli` 類型代表四個單一 qubit Pauli 運算子其中之一。
   這個型別是用來表示旋轉的基底作業，並指定要測量的可觀察。
   這是具有四個可能值的列舉型別： `PauliI`、`PauliX`、`PauliY`和 `PauliZ`，這些都是 `Pauli`類型的常數。
- `Result` 類型代表測量結果。
   這是具有兩個可能值的列舉類型： `One` 和 `Zero`，這是 `Result`類型的常數。
   `Zero` 表示已測量 + 1 eigenvalue;`One` 表示-1 eigenvalue。
- `Range` 類型代表一連串的整數，以 `start..step..stop`表示，其中表示步驟是選項。 
   這是 `start .. stop` 對應至 `start..1..stop`，例如 `1..2..7` 代表序列 $\{1、3、5、7\}$。
- `String` 類型是一系列 Unicode 字元，在使用者建立後不會受到任何不透明的排序。
  此類型是用來在發生錯誤或診斷事件時，將訊息報告給傳統主機。
- `Unit` 類型是只允許一個值 `()`的類型。 
  這個類型是用來表示 Q # 函式或作業不會傳回任何資訊。 

`true`、`false`、`PauliI`、`PauliX`、`PauliY`、`PauliZ`、`One`和 `Zero` 的常數都是 Q # 中的所有保留符號。

## <a name="array-types"></a>陣列類型

假設有任何有效的 Q # 類型 `'T`，則會有一個類型，代表 `'T`類型的值陣列。
此陣列類型會以 `'T[]`表示;例如，`Qubit[]` 或 `Int[][]`。
例如，整數的集合會以 `Int[]`表示，而 `(Bool, Pauli)` 值陣列的陣列則會以 `(Bool, Pauli)[][]`表示。

在第二個範例中，請注意這代表可能不規則的陣列陣列，而不是矩形二維陣列。
問 # 不提供對矩形多維陣列的支援。

陣列值可以使用方括弧括住陣列的元素（如 `[PauliI, PauliX, PauliY, PauliZ]`），以 Q # 原始程式碼撰寫。
陣列常值的類型取決於陣列中所有專案的通用基底類型。 

> [!WARNING]
> 建立陣列之後，就無法變更陣列的元素。
> Update-重新指派語句和（或）複製和更新運算式可以用來建立已修改的陣列。

或者，您可以使用 `new` 關鍵字，從其大小建立陣列：

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

不論是哪一種情況，一旦結構化陣列之後，就可以使用核心函式 `Length` 來取得做為 `Int`的元素數目。
陣列可以使用方括弧括住，並以具有類型 `Int` 或類型 `Range`的下標來取得單一專案或包含陣列元素子集的新陣列。
陣列的注標是以零為基底：

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>元組類型

假設有零或多個不同的類型 `T0`、`T1`、...、`Tn`，我們可以將新的*元組類型*表示為 `(T0, T1, ..., Tn)`。
用來建立新元組類型的類型本身可以是元組，如 `(Int, (Qubit, Qubit))`。
不過，這類的嵌套一定是有限的，因為在任何情況下，元組類型不能包含本身。

新元組類型的值是由元組中每個類型的值序列所組成的元組。
例如，`(3, false)` 是一個元組，其型別為 `(Int, Bool)`的元組類型。
您可以建立元組的陣列、陣列的元組、子元組的元組等等。

從 Q # 0.3，`Unit` 是空的元組的*型*別名稱;`()` 用於空的元組*值*。

元組實例為不可變。
問 # 未提供在建立後變更元組內容的機制。

元組是一種功能強大的概念，用於整個 Q #，將值一起收集成單一值，使其更容易傳遞。
特別是，使用元組標記法時，我們可以表示每個作業和可呼叫都只接受一個輸入，而且只會傳回一個輸出。

### <a name="singleton-tuple-equivalence"></a>單一元組等價

您可以建立單一（單一元素）元組，`('T1)`，例如 `(5)` 或 `([1,2,3])`。
不過，Q # 會將單一元組視為完全等同于已括住類型的值。
也就是說，`5` 和 `(5)`之間，或是 `5` 和 `(((5)))`之間，或介於 `(5, (6))` 和 `(5, 6)`之間沒有差異。

此等價適用于所有用途，包括指派和運算式。
撰寫 `5+3`的 `(5)+3` 是有效的，而且這兩個運算式都會評估為 `8`。
特別是，這表示輸入元組或輸出元組類型具有一個欄位的作業或函數，可以視為接受單一引數或傳回單一值。

我們將此屬性稱為_單一元組等價_。

## <a name="user-defined-types"></a>使用者定義類型

Q # 檔案可能會定義新的命名類型，其中包含任何合法類型的單一值。
對於 `T`的任何元組類型，我們可以宣告新的使用者自訂類型，這是使用 `newtype` 語句 `T` 的子類型。
例如，在 @"microsoft.quantum.math" 命名空間中，複數會定義為使用者定義型別：

```qsharp
newtype Complex = (Double, Double);
```

此語句會建立新的類型，其中包含兩個 `Double`類型的匿名專案。   
除了匿名專案以外，使用者定義型別也支援從 Q # 0.7 版或更高版本開始的命名專案。 例如，我們可能會將代表複數實數部分的 double `Re` 命名為專案，並為虛數部分 `Im`： 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
將使用者定義型別中的一個專案命名，並不表示所有專案都必須命名，而且支援任何組合的已命名和未命名專案。 此外，也可以將內部專案命名為。
如以下所定義的類型 `Nested` 為基礎類型 `(Double, (Int, String))`，其中只有類型 `Int` 的專案會命名為，而所有其他專案則為匿名。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
命名專案的優點是可以透過存取運算子 `::`直接存取它們。 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

若要存取另一方面的匿名專案，必須使用後置運算子 `!`將已包裝的值先解壓縮。
「解除包裝」運算子（`!`）允許將使用者定義型別中包含的值解壓縮。
這類「解除包裝」運算式的類型是使用者定義類型的基礎類型。 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

解除包裝運算子只會解除封裝一層換行。
可以使用多個解除包裝運算子來存取已相乘的值。

例如：

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

如需更多詳細資料，請參閱解除包裝[運算式](xref:microsoft.quantum.language.expressions#unwrap-expressions)和[運算子優先順序](xref:microsoft.quantum.language.expressions#operator-precedence)的一節。

使用者定義類型的值可以藉由呼叫對應的類型構造函式來建立：

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

或者，您可以使用[複製和更新運算式](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)，從現有的值建立新的值。 如同陣列，這類運算式會複製原始運算式的所有專案值，但指定的命名專案除外。 這些值會設定為運算式右邊定義的值。 任何其他語言結構（例如[update 和重新指派語句](xref:microsoft.quantum.language.statements#update-and-reassign-statement)）也適用于使用者定義類型中的已命名專案。

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

使用者定義類型可在任何其他類型可能使用的地方使用。
特別是，您可以定義使用者定義型別的陣列，並將使用者定義型別納入為元組型別的元素。

不可能建立遞迴類型結構。
也就是說，定義使用者自訂類型的類型可能不是包含使用者定義類型之元素的元組類型。
一般而言，使用者定義型別可能不會有彼此的迴圈相依性，因此下列型別定義將不合法：

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

除了為可能複雜的元組類型提供簡短的別名之外，定義這類類型的其中一個重要優點是，它們可以記錄特定值的意圖。
回到 `Complex`的範例，其中一個也可以將2D 極座標定義為使用者定義型別：

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

雖然 `Complex` 和 `Polar` 都有 `(Double, Double)`的基礎類型，但這兩個類型在 Q # 中完全不相容，因此不小心以極座標呼叫複雜數學函數的風險，反之亦然。
如此一來，使用者定義型別與中F#的記錄具有類似的角色，例如。 


## <a name="operation-and-function-types"></a>Operation 和 Function 類型

Q _# 作業_是量子副程式。
也就是說，它是包含量子作業的可呼叫常式。

Q # 函式是在量子演算法內_使用的傳統_副程式。
它可能包含傳統程式碼，但不含量子作業。
具體而言，函式可能不會配置或借用 qubits，也不可能呼叫作業。
不過，您可以傳遞作業或 qubits 進行處理。
函式在使用相同的引數呼叫這些函式時，一定會產生相同的結果。 

作業和函式統稱為_callables_。  您可以在下面看到一些[範例](#examples)。

所有 Q # callables 都會被視為採用單一值做為輸入，並傳回單一值做為輸出。
輸入和輸出值皆可為元組。
`Unit`不會傳回結果的 Callables。
沒有輸入的 Callables 會採用空的元組做為輸入。

任何可呼叫的基本類型都會寫入為 `('Tinput => 'Tresult)` 或 `('Tinput -> 'Tresult)`，其中 `'Tinput` 和 `'Tresult` 都是類型。
第一個使用 `=>`的表單用於作業;具有 `->`的第二個表單，適用于函式。
例如，`((Qubit, Pauli) => Result)` 代表可能的單一 qubit 測量作業的簽章。

函式類型是由其簽章完整指定。
例如，計算角度之正弦函數的函式會有類型 `(Double -> Double)`。

作業（但不是函式）具有特定的其他_特性_，會以運算類型的一部分來表示。 這類特性包含作業所支援之函子的相關資訊。
函子是會產生基底作業特製化的元運算;請參閱下方的[函子](#functors)。

作業類型是由其輸入類型、輸出類型和其特性所指定。    
若要在作業類型中要求支援 `Controlled` 和/或 `Adjoint` 仿函數，我們需要新增指出對應特性的注釋。
例如，注釋 `is Ctl` 表示作業是可控制的。 如果我們想要要求該類型的作業同時支援 `Adjoint` 和 `Controlled` 仿函數，我們可以將其表示為 `(Qubit => Unit is Adj + Ctl)`。 `Adj` 使用的作業特性和 `Ctl` 嚴格的說，是兩組預先定義的標籤，其中每個標籤都代表特定的作業特性，例如支援特定的仿函數。
因此，`+` 是用來指出這兩個集合的聯集，而 `*` 用來表示交集，也就是這兩個集合的通用標籤。  

例如，Pauli `X` 運算的類型 `(Qubit => Unit is Adj + Ctl)`。
不支援任何函子的作業類型是由其輸入和輸出類型單獨指定，沒有額外的注釋。


### <a name="type-parameterized-functions-and-operations"></a>型別參數化函數和作業

可呼叫類型可能包含型別參數。
型別參數是以單一引號前面加上的符號來表示。例如，`'A` 是合法的型別參數。

類型參數在單一簽章中可能會出現一次以上。
例如，將另一個函式套用至陣列之每個專案的函式，並傳回所收集的結果會有簽章 `(('A[], 'A->'A) -> 'A[])`。
同樣地，傳回兩個作業組合的函式可能會有簽章 `((('A=>'B), ('B=>'C)) -> ('A=>'C))`。

叫用型別參數化可呼叫時，所有具有相同型別參數的引數都必須屬於相同的型別。

問 # 並未提供機制來限制可能會替代類型參數的可能類型。

### <a name="type-compatibility"></a>類型相容性

具有其他函子支援的作業可以在具有較少函子的作業中使用，但預期會有相同的簽章。
例如，`(Qubit => Unit is Adj)` 類型的作業可以在預期類型 `(Qubit => Unit)` 作業的任何位置使用。

Q # 是可呼叫傳回類型的協變數：傳回類型的可呼叫 `'A` 與具有相同輸入類型的可呼叫，以及與 `'A` 相容的結果類型相容。

問 # 是相對於輸入類型的逆變性：接受型別 `'A` 做為輸入的可呼叫，與具有相同結果型別的可呼叫，以及與 `'A`相容的輸入型別相容。

也就是，假設有下列定義：

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

下列為 true：

- 函數 `ConjugateInvertWith` 可以使用 `Invert` 或 `ApplyUnitary`的 `inner` 引數來叫用。
- 函數 `ConjugateUnitaryWith` 可以使用 `ApplyUnitary`的 `inner` 引數來叫用，但不能用 `Invert`。
- 可能會從 `ConjugateInvertWith`傳回 `(Qubit[] => Unit is Adj + Ctl)` 類型的值。

> [!IMPORTANT]
> 問 # 0.3 在使用者定義型別的行為上帶來了顯著的差異。

使用者自訂類型會被視為基礎類型的包裝版本，而不是子類型。
這表示在預期基礎類型的值時，使用者自訂類型的值無法使用。

### <a name="functors"></a>函子

問 # 中的仿函數是從另一個作業定義新作業的 factory。
函子在定義新作業的執行時，可以存取基底作業的執行。
因此，函子可以執行比傳統更高層級函數更複雜的函式。

函子在 Q # 類型系統中沒有標記法。 因此目前無法將它們系結至變數，或將它們當做引數傳遞。 

仿函數的使用方式是將它套用至作業，並傳回新的作業。
例如，將 `Adjoint` 仿函數套用至 `Y` 作業所產生的作業會寫成 `Adjoint Y`。
接著就可以叫用新的作業，就像任何其他作業一樣。
因此，`Adjoint Y(q1)` 會將 Adjoint 仿函數套用至 `Y` 作業，以產生新作業，並將該新作業套用至 `q1`。

同樣地，`Controlled X(controls, target)` 會將受控制的仿函數套用至 `X` 作業，以產生新的作業，並將該新作業套用至 `controls` 和 `target`。

Q # 中的兩個標準函子是 `Adjoint` 和 `Controlled`。

#### <a name="adjoint"></a>Adjoint

在量子運算中，作業的 adjoint 是作業的複雜共軛轉置。
若為執行單一運算子的作業，則 adjoint 是運算的反向。
針對只在一組 qubits 上叫用其他單一作業順序的簡單操作，adjoint 的計算方式是將子作業的 adjoints 套用到反向序列中的相同 qubits 上。

給定作業運算式時，可以使用 `Adjoint` 仿函數來形成新的運算運算式。
例如，`Adjoint QFT` 指定 `QFT` 作業的 adjoint。
新作業的簽章和類型與基底作業相同。
特別是，新作業也允許 `Adjoint`，而且只有在基底作業執行時，才會允許 `Controlled`。

Adjoint 仿函數是它自己的反向;也就是說，`Adjoint Adjoint Op` 一律與 `Op`相同。

#### <a name="controlled"></a>管理

作業的受控制版本是新的作業，只有在所有控制項 qubits 都處於指定的狀態時，才會有效地套用基底作業。
如果控制項 qubits 在重迭中，則會將基底作業套用 coherently 至重迭的適當部分。
因此，控制的作業通常用來產生會任何牽連。

在 Q # 中，受控制的版本一律接受控制項 qubits 的陣列，而且指定的狀態一律會讓所有控制項 qubits 都處於計算（`PauliZ`） `One` 狀態，$ \ket{1}$。
藉由將適當的單一作業套用至受控制的作業之前的控制項 qubits，然後在受控制的作業之後套用單一作業的反轉，即可達成根據其他狀態進行控制。
例如，將 `X` 作業套用至受控制作業前後的控制項 qubit，會導致作業控制該 qubit 的 `Zero` 狀態（$ \ket{0}$）;在之前和之後套用 `H` 作業將會控制 `PauliX` `One` 狀態，也就是 Pauli X、$ \ket{-} \mathrel{： =} （\ket{0}-\ket{1}）/\sqrt{2}$ 而不是 `PauliZ` `One` 狀態的 1 eigenvalue。

給定作業運算式時，可以使用 `Controlled` 仿函數來形成新的運算運算式。
新作業的簽章是以原始作業的簽章為基礎。
結果型別相同，但輸入型別是具有 qubit 陣列的兩個元組，其會將控制項 qubit 保存為第一個專案，並將原始運算的引數當做第二個元素。
新的作業支援 `Controlled`，而且只有在原始作業執行時，才支援 `Adjoint`。

如果原始作業只接受單一引數，則會在這裡播放單一元組等價。
例如，`Controlled X` 是 `X` 作業的受控制版本。
`X` 的類型為 `(Qubit => Unit is Adj + Ctl)`，因此 `Controlled X` 的類型為 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`;由於單一元組等價，這與 `((Qubit[], Qubit) => Unit is Adj + Ctl)`相同。

如果基底作業接受數個引數，請記得將作業之受控制版本的對應引數括在括弧中，以將其轉換為元組。
例如，`Controlled Rz` 是 `Rz` 作業的受控制版本。
`Rz` 具有類型 `((Double, Qubit) => Unit is Adj + Ctl)`，因此 `Controlled Rz` 的類型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`。
因此，`Controlled Rz(controls, (0.1, target))` 是 `Controlled Rz` 的有效調用（請注意 `0.1, target`周圍的括弧）。

另一個範例是，`CNOT(control, target)` 可以實作為 `Controlled X([control], target)`。 如果目標應該由2個 control qubits （CCNOT）控制，我們可以使用 `Controlled X([control1, control2], target)` 語句。

### <a name="examples"></a>範例

此 Q # 作業的範例來自[量測](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement)範例。 在作業中，我們可以在這些 qubits 上配置 qubits 並使用量子作業，例如 `H` 和 `X`：

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

此函式的範例來自[PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)範例。 它包含純粹的傳統程式碼。 您可以看到，與上述範例不同的是，不會配置任何 qubits，也不會使用任何量子作業。

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

也可以將函式傳遞給 qubits 以進行處理，如下列[ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis)範例中的範例所示。 Qubits 會傳遞至函式並用於處理，雖然沒有任何點是 qubit 狀態本身已修改。

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
