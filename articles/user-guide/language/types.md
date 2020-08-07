---
title: 中的類型Q#
description: 瞭解程式設計語言中使用的不同類型 Q# 。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: b034af0b1d3b967b5680403341813407e4412f93
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869591"
---
# <a name="types-in-no-locq"></a>中的類型Q#

本文描述型別 Q# 模型和用來指定和使用型別的語法。 如需如何建立和操作這些類型運算式的詳細資訊，請參閱[類型運算式](xref:microsoft.quantum.guide.expressions)。

我們注意 Q# 到，是*強型*別語言，因此謹慎使用這些型別可協助編譯器在編譯時期提供有關程式的強式保證 Q# 。
為了盡可能提供最強的保證，中類型之間的轉換 Q# 必須使用表達該轉換的函式呼叫來明確地進行。 
Q#提供各種功能作為 <xref:microsoft.quantum.convert> 命名空間的一部分。
另一方面，Upcasts 到相容的型別，就會隱含地發生。 

Q#提供兩種基本類型，直接使用，以及從其他類型產生新類型的各種方式。
我們會在本文的其餘部分說明每個專案。

## <a name="primitive-types"></a>基本類型

Q#語言提供下列*基本類型*，您可以直接在程式中使用它們 Q# 。 您也可以使用這些基本類型來建立新的類型。

- `Int`類型代表64位帶正負號的整數，例如、、 `2` `107` `-5` 。
- `BigInt`類型代表任意大小的帶正負號整數，例如、、 `2L` `107L` `-5L` 。
   此類型是以 .NET 為基礎<xref:System.Numerics.BigInteger>
   型.

- `Double`類型代表雙精確度浮點數，例如、、 `0.0` `-1.3` `4e-7` 。
- `Bool`類型代表或的布林值 `true` `false` 。
- `Range`型別代表一連串的整數，以表示 `start..step..stop` 步驟是選擇性的。 
   例如， `start .. stop` 對應至 `start..1..stop` ，而 `1..2..7` 代表序列 $ \{ 1、3、5、7 \} $。
- `String`類型是一系列的 Unicode 字元，不是使用者建立後的不透明。
  在發生 `string` 錯誤或診斷事件的情況下，請使用類型向傳統主機報告訊息。
- `Unit`類型只能有一個值 `()` 。 
  使用此類型來表示 Q# 函數或作業不會傳回任何資訊。 
- `Qubit`型別代表量子位或 qubit。
   `Qubit`s 對使用者而言是不透明的。 除了將它們傳遞至另一個作業以外，唯一可行的作業是測試身分識別 (是否相等) 。
   最後，您會藉 `Qubit` 由呼叫量子處理器 (或量子模擬器) 上的內建指示，在上執行動作。
- `Pauli`類型代表四個單一 Qubit Pauli 運算子的其中一個。
   使用此類型來表示旋轉的基底作業，並指定要測量的可觀察。
   這是具有四個可能值的列舉類型： `PauliI` 、 `PauliX` 、 `PauliY` 和 `PauliZ` ，它們是類型的常數 `Pauli` 。
- `Result`型別代表測量結果。
   這是具有兩個可能值的列舉類型： `One` 和 `Zero` ，它們是類型的常數 `Result` 。
   `Zero`表示已測量 + 1 eigenvalue;`One`表示已測量-1 eigenvalue。

常數、、、、、、 `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 都是中的所有保留符號 Q# 。

## <a name="array-types"></a>陣列類型

* 針對任何有效的 Q# 類型，有一個類型代表該類型的值陣列。
    例如， `Qubit[]` 和 `(Bool, Pauli)[]` 代表 `Qubit` 值和 `(Bool, Pauli)` 元組值的陣列。

* 陣列陣列也是有效的。 在上一個範例中展開，陣列的陣列 `(Bool, Pauli)` 會以表示 `(Bool, Pauli)[][]` 。

> [!NOTE] 
> 這個範例 `(Bool, Pauli)[][]` 代表可能是陣列的不規則陣列，而不是矩形二維陣列。 Q#不支援矩形多維陣列。

* 您可以在 Q# 陣列的元素前後使用方括弧，以原始程式碼撰寫陣列值，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。
陣列中所有專案的通用基底類型會決定陣列常值的類型。 因此，使用沒有通用基底類型的元素來建立陣列會引發錯誤。  
如需範例，請參閱[callables 的陣列](xref:microsoft.quantum.guide.expressions#arrays-of-callables)。

    > [!WARNING]
    > 一旦建立之後，就無法變更陣列的元素。
    > 若要建立已修改的陣列，請使用[update 和-重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)或[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)。

* 或者，您可以使用關鍵字，從其大小建立陣列 `new` ：

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* 使用 core 函 `Length` 式來取得陣列中的專案數目，做為 `Int` 。
* 陣列可以是下標，以取得單一元素或包含陣列元素子集的新陣列。
陣列的注標是以零為基底，且必須是類型 `Int` 或類型 `Range` ：

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>元組類型

元組是一種強大的概念 Q# ，用來將值一起收集成單一值，讓您更輕鬆地將其傳遞。
特別是，使用元組標記法時，您可以表示每個作業和可呼叫都只接受一個輸入，而且只會傳回一個輸出。

* 假設有零或多個不同的類型 `T0` （ `T1` 、...）， `Tn` 您可以將新的*元組類型*表示為 `(T0, T1, ..., Tn)` 。
用來建立新元組類型的類型本身可以是元組，如中所示 `(Int, (Qubit, Qubit))` 。
不過，這類的嵌套一定是有限的，因為在任何情況下，元組類型不能包含本身。

* 新元組類型的值是由元組中每個類型的值序列所組成的元組。
例如， `(3, false)` 是其類型為元組類型的元組 `(Int, Bool)` 。
您可以建立元組的陣列、陣列的元組、子元組的元組等等。

* 從 Q# 0.3， `Unit` 是空元組的*類型*名稱; `()` 會用於空的元組的*值*。

* 元組實例為不可變。
Q#不提供一種機制，可在建立元組之後變更其內容。



### <a name="singleton-tuple-equivalence"></a>單一元組等價

您可以建立單一 (單一元素) 元組 `('T1)` ，例如 `(5)` 或 `([1,2,3])` 。
不過，會將 Q# 單一元組視為對等的類型值。
也就是說，和之間沒有任何差異，或介於和之間 `5` `(5)` `5` `(((5)))` ，或介於 `(5, (6))` 和之間 `(5, 6)` 。
它就如同寫入一樣有效， `(5)+3` `5+3` 這兩個運算式都會評估為 `8` 。

此等價適用于所有用途，包括指派和運算式。
假設有任何運算式，以括弧括住的相同運算式就是相同類型的運算式。
例如， `(7)` 是類型的運算式 `Int` ，是類型的運算式， `([1,2,3])` `Int[]` 而 `((1,2))` 是類型的運算式 `(Int, Int)` 。

特別是，這表示您可以查看其輸入元組或輸出元組類型具有一個欄位的作業或函式，以接受單一引數或傳回單一值。

我們將此屬性稱為_單一元組等價_。


## <a name="user-defined-types"></a>使用者定義類型

使用者定義型別宣告包含關鍵字 `newtype` ，後面接著使用者定義型別的名稱、 `=` 、有效的型別規格，以及終止的分號。

例如：

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* 每個 Q# 來源檔案可能會宣告任何數目的使用者定義類型。
* 類型名稱在命名空間中必須是唯一的，而且可能不會與作業和函式名稱衝突。
* 使用者定義類型是相異的，即使基底類型相同也是一樣。
特別是，兩個使用者自訂類型的值之間不會自動轉換，即使基礎類型相同也一樣。

### <a name="named-vs-anonymous-items"></a>名稱與匿名專案的比較

檔案 Q# 可能會定義新的命名類型，其中包含任何合法類型的單一值。
針對任何元組類型 `T` ，您可以使用語句來宣告新的使用者定義型別，這是的子類型 `T` `newtype` 。
@"microsoft.quantum.math"例如，在命名空間中，複數會定義為使用者定義型別：

```qsharp
newtype Complex = (Double, Double);
```
這個語句會建立具有兩個型別之匿名專案的新型別 `Double` 。   

除了匿名專案以外，使用者定義型別也支援*named items* Q# 0.7 版或更高版本的命名專案。 例如，您可以 `Re` 針對代表複數實數部分的雙精度浮點數，將專案命名為，而 `Im` 針對虛部： 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
將使用者定義型別中的一個專案命名，並不表示所有專案都必須命名，而且支援任何組合的已命名和未命名專案。 此外，內部專案也可以命名為。
例如，如下所定義的類型 `Nested` 具有基礎類型 `(Double, (Int, String))` ，其中只有類型的專案 `Int` 會命名為，而所有其他專案則為匿名。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

命名專案的優點是可以透過*存取運算子*直接存取它們 `::` 。 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

除了為可能複雜的元組類型提供簡短別名之外，定義這類類型的重要優點是，它們可以記錄特定值的意圖。
回到的範例 `Complex` ，其中一個也可以定義2d 極座標做為使用者定義的型別：

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

雖然 `Complex` 和兩者都 `Polar` 具有基礎類型，但這 `(Double, Double)` 兩個類型在中完全不相容 Q# ，因此不小心以極座標呼叫複雜數學函式的風險降至最低，反之亦然。

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>使用解除包裝運算子來存取匿名專案

若要存取匿名專案，請先使用後置運算子來解壓縮已包裝的值 `!` 。
使用「解除包裝」運算子， `!` 您可以解壓縮包含在使用者定義型別中的值。
這類「解除包裝」運算式的類型是使用者定義類型的基礎類型。 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

單一解除包裝運算子會解除封裝一層換行。 使用多個解除包裝運算子來存取已相乘的值。

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

如需解除包裝運算子的詳細資訊，請參閱[中 Q# 的類型運算式](xref:microsoft.quantum.guide.expressions)。

### <a name="creating-values-of-user-defined-types"></a>建立使用者自訂類型的值

藉由呼叫對應的類型來建立使用者自訂類型的值：

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

或者，您可以使用[複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)，從現有的值建立新的值。 就像使用陣列一樣，複製和更新運算式會複製原始運算式的所有專案值，但指定的命名專案除外。 針對這些例外狀況，這些專案的值是定義于運算式右手邊的值。 任何其他可用於陣列專案的語言結構（例如， [update 和重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)）也會存在於使用者定義類型中的已命名專案。

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

* 您可以在任何其他類型的任何位置使用使用者定義類型。
特別是，您可以定義使用者定義型別的陣列，並將使用者定義型別納入為元組型別的元素。

* 不可能建立遞迴類型結構。
也就是說，定義使用者定義型別的型別不能是包含使用者定義型別之元素的元組型別。
一般而言，使用者定義型別可能不會有彼此的迴圈相依性，因此下列型別定義的集合會無效：

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Operation 和 Function 類型

假設類型 `'Tinput` 和 `'Tresult` ：

* `('Tinput => 'Tresult)`這是任何*運算*的基本類型，例如 `((Qubit, Pauli) => Result)` 。
* `('Tinput -> 'Tresult)`是任何*函數*的基本類型，例如 `(Int -> Int)` 。 

這些稱為可呼叫*的簽*章。

* 所有 Q# callables 都採用單一值做為輸入，並傳回單一值做為輸出。
* 您可以針對輸入和輸出值使用元組。
* 沒有結果的 Callables 會傳回 `Unit` 。
* 沒有輸入的 Callables 會採用空的元組做為輸入。

### <a name="functors"></a>函子

函*式類型是*由其簽章完整指定。 例如，計算角度之正弦函數的函式會有類型 `(Double -> Double)` 。 

*作業*具有特定的其他特性，會表示為運算類型的一部分。 這類特性包含作業支援哪些*函子*的相關資訊。
例如，如果作業的執行依賴其他 qubits 的狀態，則它應該支援 `Controlled` 仿函數; 如果作業具有反向運算，則應該支援 `Adjoint` 仿函數。

> [!NOTE]
> 本文只討論函子如何改變作業簽章。 如需函子和作業的詳細資訊，請參閱[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。 

若要 `Controlled` 在作業類型中要求支援和/或 `Adjoint` 仿函數，您必須加入指出對應特性的注釋。
批註 `is Ctl` (例如， `(Qubit => Unit is Ctl)`) 表示作業是可控制的。 也就是說，它的執行會依賴另一個 qubit 或 qubits 的狀態。 同樣地，注釋會 `is Adj` 指出作業具有 adjoint，也就是說，它可以「反轉」，以便連續套用作業，然後將其 adjoint 狀態保留不變。 

如果您想要要求該類型的作業同時支援 `Adjoint` 和 `Controlled` 仿函數，您可以將此表示為 `(Qubit => Unit is Adj + Ctl)` 。 例如，內建的 Pauli 作業 <xref:microsoft.quantum.intrinsic.x> 具有類型 `(Qubit => Unit is Adj + Ctl)` 。 

不支援任何函子的作業類型是由其輸入和輸出類型單獨指定，沒有額外的注釋。

### <a name="type-parameterized-functions-and-operations"></a>型別參數化函數和作業

可呼叫類型可能包含*型別參數*。
使用前面加上單引號的符號來表示型別參數;例如， `'A` 是合法的型別參數。
如需如何定義型別參數化 callables 的詳細資訊和詳細資料，請參閱[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)。

類型參數在單一簽章中可能會出現一次以上。
例如，函數會將另一個函式套用至陣列的每個元素，並傳回所收集的結果具有簽章 `(('A[], 'A->'A) -> 'A[])` 。
同樣地，傳回兩個作業組合的函式具有簽章 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。

當您叫用型別參數化可呼叫時，所有具有相同型別參數的引數都必須屬於相同的型別。

Q#不會提供機制來限制使用者可能用來取代類型參數的可能類型。

## <a name="next-steps"></a>後續步驟

既然您已瞭解組成語言的所有類型 Q# ，請參閱[中 Q# 的類型運算式](xref:microsoft.quantum.guide.expressions)，以瞭解如何建立和操作這些各種類型的運算式。
