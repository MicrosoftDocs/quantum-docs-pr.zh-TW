---
title: 中的類型 Q#
description: 瞭解程式設計語言中所使用的不同類型 Q# 。
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: c4a3e6563b8cabee87d1db6b9cb1c1f1c1a7131b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835820"
---
# <a name="types-in-no-locq"></a>中的類型 Q#

本文描述型別 Q# 模型，以及用來指定和使用類型的語法。 如需有關如何建立和操作這些類型之運算式的詳細資訊，請參閱 [類型運算式](xref:microsoft.quantum.guide.expressions)。

我們注意 Q# 到這是一種 *強型* 別語言，可讓編譯器在編譯時期提供程式的強大保證，以利使用這些類型 Q# 。
為了盡可能提供最強的保證，中的型別之間的轉換 Q# 必須使用表達該轉換的函式來明確地呼叫。 
Q# 提供多個這類功能做為 <xref:microsoft.quantum.convert> 命名空間的一部分。
相反地，將至相容的型別會隱含地發生。 

Q# 提供兩種基本類型，可直接使用，以及各種不同的方式來產生其他類型的新類型。
本文的其餘部分將說明每個專案。

## <a name="primitive-types"></a>基本類型

此 Q# 語言提供下列基本型*primitive types*別，您可以直接在程式中使用這些類型 Q# 。 您也可以使用這些基本類型來建立新的類型。

- 此 `Int` 類型代表64位帶正負號的整數，例如， `2` 、 `107` 、 `-5` 。
- `BigInt`類型代表任意大小的帶正負號整數，例如，、 `2L` `107L` 、 `-5L` 。
   此類型是以 .NET 為基礎 <xref:System.Numerics.BigInteger>
   類型。

- `Double`型別代表雙精確度浮點數，例如，、 `0.0` `-1.3` 、 `4e-7` 。
- `Bool`類型代表或的布林值 `true` `false` 。
- 此 `Range` 類型代表整數序列（以表示）， `start..step..stop` 其中表示步驟是選擇性的。 
   例如， `start .. stop` 對應至 `start..1..stop` ，並 `1..2..7` 代表序列 $ \{ 1、3、5、7 \} $。
- `String`類型是一系列的 Unicode 字元，使用者一經建立就不透明。
  在發生 `string` 錯誤或診斷事件的情況下，使用類型來將訊息報告給傳統主控制項。
- 此 `Unit` 類型只能有一個值 `()` 。 
  您可以使用此類型來表示函式或作業不會傳回 Q# 任何資訊。 
- `Qubit`類型代表量子位或量子位。
   `Qubit`對使用者而言是不透明的。 除了將它們傳遞到另一個作業之外，唯一可行的作業是測試身分識別 (相等) 。
   最後，您會在 `Qubit` 量子處理器 (或量子模擬器) 上呼叫內建指令，以在上執行動作。
- 此 `Pauli` 類型代表四個單一量子位 Pauli 運算子的其中一個。
   您可以使用此類型來表示旋轉的基底作業，並指定要測量的可觀察。
   這是具有四個可能值的列舉類型： `PauliI` 、 `PauliX` 、 `PauliY` 和 `PauliZ` ，這是類型的常數 `Pauli` 。
- 此 `Result` 類型代表測量結果。
   它是具有兩個可能值的列舉類型： `One` 和 `Zero` ，這是類型的常數 `Result` 。
   `Zero` 表示已測量 + 1 eigenvalue; `One` 表示已測量-1 eigenvalue。

常數、、、、、、 `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` 和 `Zero` 都是中的所有保留符號 Q# 。

## <a name="array-types"></a>陣列類型

* 對於任何有效的 Q# 型別，都有一個代表該型別值陣列的型別。
    例如， `Qubit[]` 和 `(Bool, Pauli)[]` 表示 `Qubit` 值陣列和 `(Bool, Pauli)` 元組值。

* 陣列的陣列也有效。 展開先前的範例，陣列的陣列 `(Bool, Pauli)` 表示 `(Bool, Pauli)[][]` 。

> [!NOTE] 
> 這個範例 `(Bool, Pauli)[][]` 代表可能不規則的陣列陣列，而不是矩形的二維陣列。 Q# 不支援矩形多維度陣列。

* 陣列值可以 Q# 使用方括弧括住陣列的元素，以原始程式碼撰寫，如中所示 `[PauliI, PauliX, PauliY, PauliZ]` 。
陣列中所有專案的通用基底類型會決定陣列常值的類型。 因此，使用沒有通用基底類型的元素來建立陣列時，就會引發錯誤。  
如需範例，請參閱 [callables 陣列](xref:microsoft.quantum.guide.expressions#arrays-of-callables)。

    > [!WARNING]
    > 一旦建立之後，就無法變更陣列的元素。
    > 若要建立已修改的陣列，請使用 [更新和重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) 或 [複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)。

* 或者，您也可以使用關鍵字來建立陣列的大小 `new` ：

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* 您可以使用 core 函 `Length` 式，將陣列中的元素數目取得為 `Int` 。
* 陣列可以是下標，以取得單一元素或包含陣列元素子集的新陣列。
陣列的下標以零為基底，而且必須是類型 `Int` 或類型 `Range` ：

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>元組類型

元組是一種功能強大的概念 Q# ，可讓您將值一起收集到單一值，使其更容易傳遞。
尤其是，使用元組標記法時，您可以表示每個作業和可呼叫只會接受一個輸入，而且只會傳回一個輸出。

* 如果有零或多個不同的類型 `T0` ， `T1` `Tn` 則為，您可以將新的  *元組類型* 表示為 `(T0, T1, ..., Tn)` 。
用來建立新元組類型的型別本身可以是元組，如下所示 `(Int, (Qubit, Qubit))` 。
這類的嵌套一律是有限的，但在任何情況下，元組類型都不能包含自己。

* 新元組類型的值是元組，由元組中每個類型的值序列所組成。
例如， `(3, false)` 是其類型為元組類型的元組 `(Int, Bool)` 。
您可以建立元組的陣列、陣列的元組、子元組的元組等等。

* 從 Q# 0.3， `Unit` 是空元組的 *型* 別名稱， `()` 用於空的元組 *值* 。

* 元組實例是不可變的。
Q# 未提供在建立元組後變更其內容的機制。



### <a name="singleton-tuple-equivalence"></a>單一元組等價

您可以建立單一 (單一元素) 元組 `('T1)` ，例如 `(5)` 或 `([1,2,3])` 。
不過，會將 Q# 單一元組視為相當於包含之類型的值。
也就是說，和之間沒有任何差異，或是在和之間沒有差異 `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` 。
它就像寫入一樣有效， `(5)+3` `5+3` 這兩個運算式都會評估為 `8` 。

這種等價適用于所有用途，包括指派和運算式。
假設有任何運算式，則以括弧括住的相同運算式就是相同類型的運算式。
例如，是類型的 `(7)` 運算式 `Int` ， `([1,2,3])` 是類型的運算式， `Int[]` 而且 `((1,2))` 是型別的運算式 `(Int, Int)` 。

特別是，這表示您可以查看其輸入元組或輸出元組類型具有單一引數或傳回單一值的一或多個作業或函數。

我們將此屬性稱為 _單一元組等價_。


## <a name="user-defined-types"></a>使用者定義類型

使用者定義型別宣告由關鍵字組成 `newtype` ，後面接著使用者定義型別的名稱、 `=` 、有效的型別規格，以及結束的分號。

例如：

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* 每個 Q# 原始程式檔都可以宣告任意數量的使用者定義類型。
* 類型名稱在命名空間中必須是唯一的，而且可能不會與作業和函式名稱衝突。
* 使用者自訂類型是相異的，即使基底類型相同也是一樣。
尤其是在兩個使用者自訂類型的值之間沒有自動轉換，即使基礎類型相同也是一樣。

### <a name="named-vs-anonymous-items"></a>命名與匿名專案的比較

檔案 Q# 可以定義新的命名型別，其中包含任何合法型別的單一值。
針對任何元組型別 `T` ，您可以使用語句宣告新的使用者定義型別，這個型別是的子型別 `T` `newtype` 。
@"microsoft.quantum.math"例如，在命名空間中，複數是定義為使用者定義型別：

```qsharp
newtype Complex = (Double, Double);
```
這個語句會建立具有兩個型別匿名專案的新型別 `Double` 。   

除了匿名專案之外，使用者定義型別也支援*named items* Q# 0.7 或更高版本的命名專案。 例如，您可以將專案命名為 `Real` 代表複數實數部分的雙精度浮點數，並 `Imag` 針對虛數部分： 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
在使用者定義型別中命名一個專案並不表示所有專案都必須命名為，並支援任何已命名和未命名專案的組合。 此外，也可以將內部專案命名為。
`Nested`例如，如下列所定義的類型具有基礎類型 `(Double, (Int, String))` ，其中只會命名類型的專案 `Int` ，而所有其他專案都是匿名的。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

命名專案的優點是可以直接透過 *存取運算子*來存取它們 `::` 。 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

除了為可能複雜的元組類型提供簡短的別名，定義這類類型的主要優點是它們可以記錄特定值的意圖。
回到的範例 `Complex` ，一個也可以將極座標表示定義為使用者定義型別：

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

雖然 `Complex` 和兩者都 `ComplexPolar` 具有基礎類型，但是這 `(Double, Double)` 兩種類型在中完全不相容 Q# ，因此可將不小心呼叫複雜數學函式的風險降至最低，反之亦然。

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>使用解除包裝運算子存取匿名專案

若要存取匿名專案，請先使用後置運算子來將包裝值解壓縮 `!` 。
使用「解除包裝」運算子時， `!` 您可以將使用者定義型別中包含的值解壓縮。
這種類型的「解除包裝」運算式是使用者定義型別的基礎型別。 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

單一解除包裝運算子會解除包裝一層換行。 使用多個解除包裝運算子來存取相乘的值。

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

如需解除包裝運算子的詳細資訊，請參閱[中 Q# 的型別運算式](xref:microsoft.quantum.guide.expressions)。

### <a name="creating-values-of-user-defined-types"></a>建立使用者自訂類型的值

藉由呼叫對應的型別函式來建立使用者自訂類型的值：

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

或者，您可以使用 [複製和更新運算式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)，從現有的值建立新的值。 如同使用陣列，複製和更新運算式會複製原始運算式的所有專案值，但指定的命名專案除外。 針對這些例外狀況，這些專案的值是在運算式右邊定義的值。 任何其他適用于陣列專案的語言結構，例如 [更新和重新指派語句](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)，也存在於使用者定義型別中的命名專案。

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

* 您可以使用任何其他類型之任何地方的使用者自訂類型。
尤其是，您可以定義使用者定義型別的陣列，並將使用者定義型別包含為元組類型的元素。

* 不可能建立遞迴類型結構。
也就是說，定義使用者定義型別的型別不能是包含使用者定義型別之元素的元組類型。
更常見的情況是，使用者定義型別可能沒有彼此的迴圈相依性，因此下列類型定義集合無效：

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>Operation 和 Function 類型

假設類型 `'Tinput` 和 `'Tresult` ：

* `('Tinput => 'Tresult)` 是任何 *運算*的基本類型，例如 `((Qubit, Pauli) => Result)` 。
* `('Tinput -> 'Tresult)` 是任何 *函數*的基本類型，例如 `(Int -> Int)` 。 

這些稱為可呼叫 *的簽* 章。

* 所有 Q# callables 都採用單一值作為輸入，並傳回單一值作為輸出。
* 您可以針對輸入和輸出值使用元組。
* 沒有結果的 Callables，return `Unit` 。
* 沒有輸入的 Callables 會將空的元組視為輸入。

### <a name="functors"></a>函子

函*式類型是*由其簽章完全指定。 例如，計算角度正弦的函式會有型別 `(Double -> Double)` 。 

*作業* 具有某些其他特性，表示為作業類型的一部分。 這類特性包含作業所支援之 *函子* 的相關資訊。
例如，如果執行作業依賴其他量子位的狀態，則它應該支援 `Controlled` 仿函數; 如果作業具有反向，則應該支援 `Adjoint` 仿函數。

> [!NOTE]
> 本文僅討論函子如何改變作業簽章。 如需函子和作業的詳細資訊，請參閱[中的 Q# 作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。 

若要 `Controlled` 在作業類型中要求和/或仿函數的支援 `Adjoint` ，您必須加入指出對應特性的注釋。
批註 `is Ctl` (例如， `(Qubit => Unit is Ctl)`) 表示作業可控制。 也就是說，它的執行依賴另一個量子位或量子位的狀態。 同樣地，批註也會 `is Adj` 指出作業具有 adjoint，也就是它可以「反轉」，以便連續套用作業，然後將其 adjoint 狀態保持不變。 

如果您想要要求該類型的作業同時支援 `Adjoint` 和 `Controlled` 仿函數，您可以將它表示為 `(Qubit => Unit is Adj + Ctl)` 。 例如，內建的 Pauli 作業 <xref:microsoft.quantum.intrinsic.x> 具有類型 `(Qubit => Unit is Adj + Ctl)` 。 

不支援任何函子的作業類型是由其輸入和輸出類型單獨指定，不含其他注釋。

### <a name="type-parameterized-functions-and-operations"></a>類型參數化函數和作業

可呼叫的類型可以包含 *型別參數*。
使用前面加上單引號的符號來指出型別參數;例如， `'A` 是合法的型別參數。
如需如何定義型別參數化 callables 的詳細資訊和詳細資訊，請參閱[中 Q# 的作業和函數](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)。

類型參數在單一簽章中可能會出現一次以上。
例如，函式會將另一個函式套用至陣列的每個元素，並傳回所收集的結果 `(('A[], 'A->'A) -> 'A[])` 。
同樣地，傳回兩個作業組合的函式會有簽章 `((('A=>'B), ('B=>'C)) -> ('A=>'C))` 。

當您叫用型別參數化的可呼叫時，具有相同類型參數的所有引數都必須屬於相同類型。

Q# 不會提供一種機制，以限制使用者可能用來取代類型參數的可能類型。

## <a name="next-steps"></a>後續步驟

現在您已瞭解組成語言的所有 Q# 型別，請參閱[ Q# 中的型別運算式](xref:microsoft.quantum.guide.expressions)，以瞭解如何建立和操作這些各種類型的運算式。
