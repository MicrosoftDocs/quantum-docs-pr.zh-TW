---
title: Q 中的類型#
description: '瞭解問答 # 程式設計語言中使用的不同類型。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 58370193bd62e306197a9e07c28f8611f043e55c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431133"
---
# <a name="types-in-q"></a>Q 中的類型#

此頁面會配置 Q # 類型模型，並描述用於指定和使用類型的語法。
下一個頁面 [[類型運算式](xref:microsoft.quantum.guide.expressions)] 會詳細說明如何建立和操作這些類型的運算式。

我們注意到，Q # 是*強型*別語言，因此小心使用這些型別可協助編譯器在編譯時期提供有關 Q # 程式的強式保證。
為了提供最強的保證，在 Q # 中類型之間的轉換必須使用表達該轉換的函式呼叫來明確地進行。 在命名空間中提供各種不同的函式 <xref:microsoft.quantum.convert> 。
另一方面，Upcasts 到相容的型別就會隱含地發生。 

Q # 同時提供兩種基本類型，可以直接使用，以及從其他類型產生新類型的各種方式。
我們會在本節的其餘部分說明每個。

## <a name="primitive-types"></a>基本類型

Q # 語言提供了數種*基本類型*，可從中建造其他類型：

- `Int`型別代表64位帶正負號的整數，例如： `2` 、 `107` 、 `-5` 。
- `BigInt`類型代表任意大小的帶正負號整數，例如、 `2L` `107L` 、 `-5L` 。
   此類型是以 .NET 為基礎<xref:System.Numerics.BigInteger>
   型.
- `Double`型別代表雙精確度浮點數，例如： `0.0` 、 `-1.3` 、 `4e-7` 。
- 此 `Bool` 類型代表布林值，可以是 `true` 或 `false` 。
- `Range`型別代表一連串的整數，以表示 `start..step..stop` 步驟是選項。 
   這會 `start .. stop` 對應至 `start..1..stop` ，例如 `1..2..7` 代表序列 $ \{ 1、3、5、7 \} $。
- `String`類型是一系列的 Unicode 字元，不是使用者建立後的不透明。
  此類型是用來在發生錯誤或診斷事件時，將訊息報告給傳統主機。
- `Unit`類型是只允許一個值的類型 `()` 。 
  這個類型是用來表示 Q # 函式或作業不會傳回任何資訊。 
- `Qubit`型別代表量子位或 qubit。
   `Qubit`對使用者而言，是不透明的;除了將它們傳遞至另一個作業以外，唯一可行的作業是測試身分識別（相等）。
   最後，的動作 `Qubit` 是藉由呼叫量子處理器上的內建指示來執行（或模擬）。
- `Pauli`類型代表四個單一 Qubit Pauli 運算子的其中一個。
   這個型別是用來表示旋轉的基底作業，並指定要測量的可觀察。
   這是列舉型別，其中包含四個可能 `PauliI` 的值：、 `PauliX` 、 `PauliY` 和 `PauliZ` ，這是類型的常數 `Pauli` 。
- `Result`型別代表測量結果。
   這是具有兩個可能值的列舉類型： `One` 和 `Zero` ，它們是類型的常數 `Result` 。
   `Zero`表示已測量 + 1 eigenvalue;`One`表示-1 eigenvalue。

常數 `true` 、、、、、、 `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 都是 Q # 中的所有保留符號。

## <a name="array-types"></a>陣列類型

假設有任何有效的 Q # 類型 `'T` ，則會有代表類型值陣列的類型 `'T` 。
這個陣列型別會表示為 `'T[]` ; 例如， `Qubit[]` 或 `Int[][]` 。
例如，整數的集合是以表示 `Int[]` ，而值陣列的陣列 `(Bool, Pauli)` 則是表示 `(Bool, Pauli)[][]` 。

在第二個範例中，請注意這代表可能不規則的陣列陣列，而不是矩形二維陣列。
問 # 不提供對矩形多維陣列的支援。

您可以使用方括弧括住陣列的元素，將陣列值寫入至 Q # 原始程式碼中，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。
陣列常值的類型取決於陣列中所有專案的通用基底類型。 

> [!WARNING]
> 建立陣列之後，就無法變更陣列的元素。
> [Update-重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)和（或）[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)可以用來建立已修改的陣列。

或者，您可以使用關鍵字，從其大小建立陣列 `new` ：

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

不論是哪一種情況，一旦結構化陣列之後， `Length` 就可以使用核心函式來取得專案的數目 `Int` 。
陣列可以使用方括弧（具有類型或類型的注標）來做為下標 `Int` `Range` ，以取得單一專案或包含陣列元素子集的新陣列。
陣列的注標是以零為基底：

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>元組類型

假設有零或多個不同的類型 `T0` ， `T1` ，...， `Tn` 我們可以將新的*元組類型*表示為 `(T0, T1, ..., Tn)` 。
用來建立新元組類型的類型本身可以是元組，如中所示 `(Int, (Qubit, Qubit))` 。
不過，這類的嵌套一定是有限的，因為在任何情況下，元組類型不能包含本身。

新元組類型的值是由元組中每個類型的值序列所組成的元組。
例如， `(3, false)` 是其類型為元組類型的元組 `(Int, Bool)` 。
您可以建立元組的陣列、陣列的元組、子元組的元組等等。

從 Q # 0.3， `Unit` 是空元組的*型*別名稱， `()` 用於空的元組*值*。

元組實例為不可變。
問 # 未提供在建立後變更元組內容的機制。

元組是一種功能強大的概念，用於整個 Q #，將值一起收集成單一值，使其更容易傳遞。
特別是，使用元組標記法時，我們可以表示每個作業和可呼叫都只接受一個輸入，而且只會傳回一個輸出。

### <a name="singleton-tuple-equivalence"></a>單一元組等價

您可以建立單一（單一元素）元組， `('T1)` 例如 `(5)` 或 `([1,2,3])` 。
不過，Q # 會將單一元組視為完全等同于已括住類型的值。
也就是說，和之間沒有任何差異，或介於和之間 `5` `(5)` `5` `(((5)))` ，或介於 `(5, (6))` 和之間 `(5, 6)` 。
這就是寫入 `(5)+3` 為寫入的有效值 `5+3` ，而且這兩個運算式會評估為 `8` 。

此等價適用于所有用途，包括指派和運算式。
假設有任何運算式，以括弧括住的相同運算式就是相同類型的運算式。
例如， `(7)` 是 `Int` 運算式， `([1,2,3])` 是 s 類型的運算式 `Int` ，而是型別為的 `((1,2))` 運算式 `(Int, Int)` 。

特別是，這表示輸入元組或輸出元組類型具有一個欄位的作業或函數，可以視為接受單一引數或傳回單一值。

我們將此屬性稱為_單一元組等價_。


## <a name="user-defined-types"></a>使用者定義類型

使用者定義型別宣告包含關鍵字 `newtype` ，後面接著使用者定義型別的名稱、 `=` 、有效的型別規格，以及終止的分號。

例如：

```qsharp
newtype PairOfInts = (Int, Int);
```

每個 Q # 來源檔案都可以宣告任何數目的使用者定義類型。
類型名稱在命名空間中必須是唯一的，而且可能不會與作業和函式名稱衝突。

即使基底類型完全相同，使用者定義類型也是相異的。
特別是，兩個使用者自訂類型的值之間不會自動轉換，即使基礎類型相同也一樣。

### <a name="named-vs-anonymous-items"></a>名稱與匿名專案的比較

Q # 檔案可能會定義新的命名類型，其中包含任何合法類型的單一值。
針對任何元組類型 `T` ，我們可以宣告新的使用者自訂類型，這是具有語句的子類型 `T` `newtype` 。
例如，在 @"microsoft.quantum.math" 命名空間中，複數會定義為使用者定義型別：

```qsharp
newtype Complex = (Double, Double);
```
這個語句會建立具有兩個型別之匿名專案的新型別 `Double` 。   

除了匿名專案以外，使用者定義型別也支援從 Q # 0.7 版或更高版本開始的*命名專案*。 例如，我們可以將 `Re` 代表複數實數部分之 double 的專案命名為，並 `Im` 為虛數部分指定： 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
將使用者定義型別中的一個專案命名，並不表示所有專案都必須命名，而且支援任何組合的已命名和未命名專案。 此外，內部專案也可以命名為。
例如， `Nested` 下列定義的類型具有基礎類型 `(Double, (Int, String))` ，其中只有類型的專案 `Int` 會命名為，而所有其他專案則為匿名。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

命名專案的優點是可以透過*存取運算子*直接存取它們 `::` 。 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

除了為可能複雜的元組類型提供簡短的別名之外，定義這類類型的其中一個重要優點是，它們可以記錄特定值的意圖。
回到的範例 `Complex` ，其中一個也可以定義2d 極座標做為使用者定義的型別：

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

雖然和都 `Complex` `Polar` 具有基礎類型，但這 `(Double, Double)` 兩個類型在 Q # 中完全不相容，因此不小心以極座標呼叫複雜數學函式的風險降至最低，反之亦然。
如此一來，使用者定義型別與 F # 中的記錄具有類似的角色，例如。 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>使用解除包裝運算子來存取匿名專案

若要存取另一方面的匿名專案，必須使用後置運算子來解壓縮已包裝的值 `!` 。
「解除包裝」運算子 `!` 可讓將使用者定義型別中包含的值解壓縮。
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

如需解除包裝運算子的詳細資訊，請參閱[Q # 中的類型運算式](xref:microsoft.quantum.guide.expressions)。

### <a name="creating-values-of-user-defined-types"></a>建立使用者自訂類型的值

使用者自訂類型的值可以藉由呼叫對應的類型的函式來建立：

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

或者，您可以使用[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)，從現有的值建立新的值。 如同陣列，這類運算式會複製原始運算式的所有專案值，但指定的命名專案除外。 這些值會設定為運算式右邊定義的值。 任何其他語言結構（例如[update 和重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)）也適用于使用者自訂類型中的名稱專案。

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

請注意，不可能建立遞迴類型結構。
也就是說，定義使用者自訂類型的類型可能不是包含使用者定義類型之元素的元組類型。
一般而言，使用者定義型別可能不會有彼此的迴圈相依性，因此下列型別定義將不合法：

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a>Operation 和 Function 類型

任何可呼叫的基本類型都會寫入為 `('Tinput => 'Tresult)` 或 `('Tinput -> 'Tresult)` ，其中 `'Tinput` 和 `'Tresult` 都是類型。
這些稱為可呼叫*的簽*章。

所有 Q # callables 都會被視為採用單一值做為輸入，並傳回單一值做為輸出。
輸入和輸出值皆可為元組。
沒有傳回結果的 Callables `Unit` 。
沒有輸入的 Callables 會採用空的元組做為輸入。

> [!NOTE]
> 第一個使用的形式 `=>` 會用於作業，第二個表單則用於函式 `->` 。
> 例如， `((Qubit, Pauli) => Result)` 代表可能的單一 qubit 測量作業的簽章。
函*式類型是*由其簽章完整指定。
例如，計算角度之正弦函數的函式會有類型 `(Double -> Double)` 。

*作業*---但不是函式---會有特定的其他特性，會表示為操作類型的一部分。 這類特性包含作業所支援之*函子*的相關資訊。
例如，如果作業的執行可以根據其他 qubits 的狀態進行條件運算，它應該支援 `Controlled` 仿函數; 如果作業具有反向運算，則應該支援 `Adjoint` 仿函數。 在[Q # 的作業和](xref:microsoft.quantum.guide.operationsfunctions)函式中會詳細討論函子和作業，但這裡我們只會討論這會如何改變作業簽章。

若要在作業 `Controlled` 類型中要求支援和/或 `Adjoint` 仿函數，我們需要新增指出對應特性的注釋。
注釋 `is Ctl` （例如 `(Qubit => Unit is Ctl)` ）表示作業可控制---也就是，它是在另一個 qubit 或 qubits 的狀態下執行。 同樣地， `is Adj` 表示作業具有 adjoint; 或者只是「反轉」，這樣會連續套用作業，而其 adjoint 狀態會使狀態保持不變。 

如果我們想要要求該類型的作業同時支援 `Adjoint` 和 `Controlled` 仿函數，我們可以將此表示為 `(Qubit => Unit is Adj + Ctl)` 。 例如，內建的 Pauli 作業 <xref:microsoft.quantum.intrinsic.x> 具有類型 `(Qubit => Unit is Adj + Ctl)` 。 

不支援任何函子的作業類型是由其輸入和輸出類型單獨指定，沒有額外的注釋。

### <a name="type-parameterized-functions-and-operations"></a>型別參數化函數和作業

可呼叫類型可能包含型別參數。
型別參數是以單一引號前面加上的符號來表示。例如， `'A` 是合法的型別參數。
如需定義型別參數化 callables 的詳細資料，請[至 Q # 頁面中的作業和函數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)。

類型參數在單一簽章中可能會出現一次以上。
例如，將另一個函式套用至陣列之每個專案的函式，並傳回所收集的結果會有簽章 `(('A[], 'A->'A) -> 'A[])` 。
同樣地，傳回兩個作業組合的函式可能會有簽章 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。

叫用型別參數化可呼叫時，所有具有相同型別參數的引數都必須屬於相同的型別。

問 # 並未提供機制來限制可能會替代類型參數的可能類型。

## <a name="whats-next"></a>下一步
既然您已瞭解組成 Q # 語言的所有類型，您可以前往[q # 中的類型運算式](xref:microsoft.quantum.guide.expressions)，以瞭解如何建立和操作這些各種類型的運算式。


