---
title: 'Q # 語句 |Microsoft Docs'
description: 'Q # 語句'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184860"
---
# <a name="statements-and-other-constructs"></a>語句和其他結構

## <a name="comments"></a>註解

批註的開頭為兩個正斜線，`//`，並繼續直到行尾為止。
批註可能會出現在 Q # 來源檔案中的任何位置。

### <a name="documentation-comments"></a>檔批註

當編譯器在命名空間、作業、特製化、函式或類型定義之前出現時，會以特殊方式處理開頭為三個正斜線（`///`）的批註。
在此情況下，會將其內容視為已定義之可呼叫或使用者定義類型的檔，就像其他 .NET 語言一樣。

在 `///` 批註中，顯示為 API 檔一部分的文字會格式化為[Markdown](https://daringfireball.net/projects/markdown/syntax)，並以特殊命名的標頭指出檔的不同部分。
如需 Markdown 的延伸模組，可以使用 `@"<ref target>"`包含 Q # 中作業、函式和使用者定義類型的交互參考，其中 `<ref target>` 會由所參考之程式碼物件的完整名稱取代。
（選擇性）檔引擎也可能支援其他 Markdown 延伸模組。

例如：

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

下列名稱會被辨識為檔批註標頭。

- **摘要**：函數或作業行為的簡短摘要，或類型的用途。 摘要的第一個段落用於暫留資訊。 它應該是純文字。
- **描述**：函數或作業行為的描述，或類型的用途說明。 摘要和描述會串連，以形成函式、作業或類型所產生的檔檔案。
  描述可以包含內嵌 LaTeX 格式的符號和方程式。
- **輸入**：作業或函數之輸入元組的描述。
  可能包含其他 Markdown 子區段，指示輸入元組的每個個別元素。
- **輸出**：作業或函式所傳回之元組的描述。
- **型別參數**：空的區段，其中包含每個泛型型別參數的一個額外子節。
- **範例**：使用中的作業、函數或類型的簡短範例。
- **備註**：其他 prose，描述作業、函數或類型的某些層面。
- **另請參閱**：表示相關函數、作業或使用者定義類型的完整名稱清單。
- **參考**：要記載之專案的參考和引文清單。

## <a name="namespaces"></a>命名空間

每個 Q # 作業、函式和使用者定義類型都定義在命名空間中。
問 # 遵循與其他 .NET 語言相同的命名規則。
不過，Q # 不支援命名空間的相對參考。
也就是說，如果已開啟命名空間 `a.b`，`c.d` 的作業名稱參考將不會解析為完整名稱 `a.b.c.d`的作業。

在命名空間區塊內，`open` 指示詞可用來匯入特定命名空間中宣告的所有類型和 callables，並依其不合格的名稱加以參考。 （選擇性）可能會定義已開啟之命名空間的簡短名稱，讓來自該命名空間的所有元素都可以（和需要）以定義的簡短名稱限定。 `open` 指示詞適用于檔案內的整個命名空間區塊。

在未于目前命名空間中開啟的另一個命名空間中定義的類型或可呼叫，必須以其完整名稱來參考。
例如，除非先前已在目前區塊中開啟 `X.Y` 命名空間，否則 `X.Y` 命名空間中名為 `Op` 的作業必須由其完整名稱 `X.Y.Op`參考。 如上所述，即使已開啟 `X` 的命名空間，也無法以 `Y.Op`的方式來參考作業。
如果已在該命名空間和檔案中定義 `X.Y` 的簡短名稱 `Z`，則 `Op` 必須稱為 `Z.Op`。 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

通常最好是使用 `open` 指示詞來加入命名空間。
如果兩個命名空間定義具有相同名稱的結構，而且目前來源使用兩者的結構，則必須使用完整名稱。

## <a name="formatting"></a>格式化

大部分的 Q # 語句和指示詞的結尾都是終止的分號，`;`。
語句和宣告（例如 `for` 和 `operation` 以語句區塊結尾）不需要終止分號。
每個語句描述都會說明結尾分號是否為必要。

語句（例如運算式、宣告和指示詞）可能會細分成多行。
應避免在單一行上使用多個語句。

## <a name="statement-blocks"></a>語句區塊

Q # 語句會分組到語句區塊中。
語句區塊會以開啟的 `{` 開頭，並以結尾 `}`結束。

在另一個區塊中以詞法括住的語句區塊，會被視為包含區塊的子區塊;包含和子區塊也稱為外部和內部區塊。

## <a name="symbol-binding-and-assignment"></a>符號系結和指派

Q # 區分可變和不可變的符號。
一般來說，我們鼓勵使用不可變的符號，因為它可讓編譯器執行更多的優化。

系結的左邊是由符號元組和運算式的右手邊所組成。

由於所有 Q # 類型都是實值型別-qubits 採用有點特殊的角色，因此，當值系結至符號或符號重新系結時，就會建立「複製」。 也就是說，問 # 的行為與在指派時建立複本相同。 這也特別包括陣列。 當然，實際上只有相關的部分會在需要時重新建立。 

### <a name="tuple-deconstruction"></a>元組解構

如果系結的右手邊是元組，則該元組在指派時可能會解構。
這類解構可能牽涉到嵌套的元組，只要右側元組的形狀與符號元組的形狀相容，任何完整或部分解構都是有效的。
當 `=` 的右手邊為元組值運算式時，也可以特別使用元組解構。

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>不可變的符號

不可變的符號會使用 `let` 語句來系結。
這大致等同于中的變數宣告和初始化（例如C#），不同之處在于問 # 符號在系結之後可能不會變更;`let` 系結是不可變的。

不可變的系結包含關鍵字 `let`，後面接著符號或符號元組、等號 `=`、用來系結符號的運算式，以及終止的分號。
系結符號的類型是根據右手邊的運算式來推斷。

### <a name="mutable-symbols"></a>可變符號

可變動的符號會使用 `mutable` 語句來定義和初始化。
宣告和系結為 `mutable` 語句之一部分的符號，在稍後的程式碼中可能會重新系結至不同的值。 

可變動的系結語句包含關鍵字 `mutable`，後面接著符號或符號元組、等號 `=`、用來系結符號的運算式，以及終止的分號。
系結符號的類型是根據右手邊的運算式來推斷。 如果稍後在程式碼中重新系結符號，它的類型不會變更，而且系結的值必須與該類型相容。

### <a name="rebinding-of-mutable-symbols"></a>可變動符號的重新系結

可變動的變數可能會使用 `set` 語句來重新系結。
這類重新系結包含關鍵字 `set`，後面接著符號或符號元組、等號 `=`、將符號重新系結至的運算式，以及終止的分號。
此值必須與所系結之符號的類型相容。

#### <a name="apply-and-reassign-statement"></a>Apply-重新指派語句

我們稱為 apply 和-重新指派語句的一種特殊類型的集合語句，會在右側包含二元運算子的應用程式，並將結果重新系結至運算子的左邊引數時，提供便利的串連方式。 例如，
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
在 `for` 迴圈的每個反復專案中，遞增計數器 `counter` 的值。 上述程式碼相當於 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
所有二元運算子都有類似的語句，其中左邊的型別符合運算式型別。 這會提供一個簡單的方法來累積值：
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Update-重新指派語句

右手邊的複製和更新運算式會有類似的串連。 同樣地，使用者定義型別中的命名專案以及陣列專案的更新和重新指派語句也會存在。  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

在陣列的案例中，我們的標準程式庫包含許多常見陣列初始化和操作需求所需的工具，因此可協助避免必須在一開始就更新陣列專案。 Update-重新指派語句會在需要時提供替代方法：

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> 利用 <xref:microsoft.quantum.arrays>中提供的工具，避免不必要地使用 update 和重新指派語句。

函式
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
例如，您可以使用 `Microsoft.Quantum.Arrays`中的函式 `ConstantArray` 來簡化，並傳回復制和更新運算式：

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a>系結範圍

一般而言，符號系結會超出範圍，而且會在其發生的語句區塊結尾處變成無法執行。
此規則有兩個例外狀況：

- `for` 迴圈之迴圈變數的系結是在 for 迴圈主體的範圍內，而不是在迴圈結束之後。
- `repeat`/`until` 迴圈（主體、測試和修復）的三個部分會視為單一範圍，因此在本文中系結的符號會在測試和修復中提供。

對於這兩種類型的迴圈，每次通過迴圈都會在其本身的範圍中執行，因此在稍後的階段中，不會提供來自較早階段的系結。

內部區塊會繼承外部區塊的符號系結。
符號只能系結每個區塊一次;定義符號的名稱與範圍內的另一個符號（不是「遮蔽」）並不合法。
下列順序會是合法的：

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

與

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

但這不合法：

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

如下所示：

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a>控制流程

### <a name="for-loop"></a>For 迴圈

`for` 語句支援整數範圍或陣列上的反復專案。
語句包含關鍵字 `for`、左括弧 `(`，後面接著符號或符號元組、關鍵字 `in`、`Range` 或陣列類型的運算式、右括弧 `)`和語句區塊。

語句區塊（迴圈的主體）會重複執行，其中已定義的符號（迴圈變數）會系結至範圍或陣列中的每個值。
請注意，如果範圍運算式評估為空的範圍或陣列，則完全不會執行主體。
在進入迴圈之前，會完整評估運算式，而且在執行迴圈時不會變更。

宣告之符號的系結是不可變的，並遵循與其他變數系結相同的規則。 特別的是，在指派給迴圈變數時，可能會在陣列上進行反覆運算的陣列專案（例如）。

例如，

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

迴圈變數會系結至迴圈主體的每個進入，並在主體結尾處解除系結。
特別是，在 for 迴圈完成之後，迴圈變數不會系結。

### <a name="repeat-until-success-loop"></a>重複直到-成功迴圈

`repeat` 語句支援「重複直到成功」模式的量子。
其中包含關鍵字 `repeat`，後面接著語句區塊（_迴圈_主體）、關鍵字 `until`、布林運算式，以及結尾的分號或關鍵字 `fixup` 後面接著另一個語句區塊（_修復_）。
「迴圈主體」、「條件」和「修復」全都視為單一範圍，因此本文中系結的符號會出現在條件和修復中。

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

執行迴圈主體，然後評估條件。
如果條件為 true，則表示語句已完成;否則，會執行修復，並從迴圈主體開始重新執行語句。
請注意，完成修復的執行會結束語句的範圍，因此在本文或修復期間所做的符號系結，無法用於後續的重複。

例如，下列程式碼是使用 Hadamard 和 T 閘道 $V _3 = （\boldone + 2 i Z）/\sqrt{5}$ 執行重要旋轉閘道的概率電路。
迴圈會平均終止8/5 重複。
如需詳細資訊，請參閱[*重複直到成功：單一 qubit unitaries 的非決定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> 避免在函式內使用重複-成功迴圈。 對應的功能是由函式中的迴圈所提供。 

### <a name="while-loop"></a>While 迴圈

重複直到-成功模式具有非常量子特定的含意。 它們廣泛用於特定的量子演算法類別中，因此是 Q # 中的專用語言結構。 不過，根據條件中斷的迴圈，在編譯時期，其執行長度會是未知的，需要在量子執行時間中特別小心處理。 另一方面，它們在函式中的用法是 unproblematic，因為這些只包含將在傳統（非量子）硬體上執行的程式碼。 

問 # 因此僅支援在函式內使用 while 迴圈。 `while` 語句包含關鍵字 `while`、左括弧 `(`、條件（例如布林運算式）、右括弧 `)`和語句區塊。
只要條件評估為 `true`，就會執行語句區塊（迴圈的主體）。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>條件陳述式

`if` 語句支援條件式執行。
其中包含關鍵字 `if`、左括弧 `(`、布林運算式、右括弧 `)`，以及語句區塊（ _then_區塊）。
後面可能會接著任意數目的 else if 子句，其中每個都包含關鍵字 `elif`、左括弧 `(`、布林運算式、右括弧 `)`和語句區塊（ _else-if_區塊）。
最後，語句可能會選擇性地以 else 子句完成，其中包含關鍵字 `else` 後面接著另一個語句區塊（ _else_區塊）。
條件會進行評估，如果為 true，則會執行 then 區塊。
如果條件為 false，則會評估第一個 else if 條件;如果是 true，則為，否則為。
否則，會先測試第二個 [if] 區塊，然後再進行第三個，直到出現具有 true 條件的子句，或沒有其他的 if 子句為止。
如果原始 if 條件和所有 else if 子句評估為 false，則會執行 else 區塊（如果有提供的話）。

請注意，執行的任何區塊會在其本身的範圍中執行。
在 if 語句結尾之後，不會顯示在 then、if、或 else 區塊內進行的系結。

例如，

```qsharp
if (result == One) {
    X(target);
} 
```

或

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>傳回

Return 語句會結束執行作業或函數，並將值傳回給呼叫者。
其中包含關鍵字 `return`，後面接著適當類型的運算式和結束分號。

可呼叫會傳回空的元組，`()`，不需要 return 語句。
如果需要提早結束，在此情況下，可能會用到 `return ()`。
傳回任何其他類型的 Callables 都需要最終傳回語句。

作業中沒有 return 語句的最大數目。
如果語句在區塊內遵循 return 語句，則編譯器可能會發出警告。

例如，

```qsharp
return 1;
```

或

```qsharp
return ();
```

或

```qsharp
return (results, qubits);
```

### <a name="fail"></a>不合格

Fail 語句會結束執行作業，並將錯誤值傳回給呼叫者。
其中包含關鍵字 `fail`，後面接著字串和結尾的分號。
字串會傳回給傳統驅動程式，做為錯誤訊息。

作業內的 fail 語句數目沒有任何限制。
如果語句在區塊內遵循 fail 語句，則編譯器可能會發出警告。

例如，

```qsharp
fail $"Impossible state reached";
```

或

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Qubit 管理

請注意，函式的主體中不允許任何這些語句。
只有在作業內才有效。

### <a name="clean-qubits"></a>清除 Qubits

`using` 語句是用來取得語句區塊期間使用的新 qubits。
Qubits 保證會初始化為計算 `Zero` 狀態。
Qubits 應該位於語句區塊結尾的計算 `Zero` 狀態;建議使用模擬器來強制執行。

語句包含關鍵字 `using`，後面接著左括弧 `(`、系結、右括弧 `)`，以及可使用 qubits 的語句區塊。
系結遵循與 `let` 語句相同的模式：單一符號或符號的元組，後面接著等號 `=`，以及單一值或相符的初始化運算式元組。
初始化運算式適用于單一 qubit，表示為 `Qubit()`或 qubits 陣列，以 `Qubit[`、`Int` 運算式和 `]`表示。

例如，

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a>已變更 Qubits

`borrowing` 語句是用來取得暫時使用的 qubits。 語句包含關鍵字 `borrowing`，後面接著左括弧 `(`、系結、右括弧 `)`，以及可使用 qubits 的語句區塊。
系結會遵循與 `using` 語句中的相同模式和規則。

例如，

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

借用的 qubits 處於不明狀態，超出語句區塊結尾的範圍。
借方會認可，使 qubits 處於借用時的相同狀態，也就是其在語句區塊開頭和結尾的狀態應該是相同的。
此狀態特別不一定是傳統狀態，因此在大部分情況下，借用範圍不應包含測量。 

這種 qubits 通常稱為「中途 ancilla」。
如需已中途 Svore 使用的範例，請參閱[*使用具有以 Toffoli 為基礎的模組化乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 ancilla 2017）的 2n + 2 qubits 進行的分解。

當借用 qubits 時，系統會先嘗試從使用中的 qubits 填入要求，但在 `borrowing` 語句的本文中不會存取。
如果沒有足夠的 qubits，則會配置新的 qubits 來完成要求。

## <a name="conjugations"></a>動詞變化

相較于傳統的位，釋出配量記憶體會稍微複雜一點，因為如果 qubits 仍光子，則盲目重設 qubits 可能會對其餘的計算造成不想要的效果。 在釋放記憶體之前，適當地「復原」執行的計算，可以避免這種情況。 量子運算的常見模式如下： 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

：新的：從0.9 版開始，我們支援 conjugation 語句來執行上述轉換。 使用該語句，可以透過下列方式來執行作業 `ApplyWith`：

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
如果外部和內部轉換無法立即當做作業使用，這類 conjugation 語句會變得更有用，但以多個語句所組成的區塊來描述會更方便。 

在區塊內定義的語句的反向轉換會由編譯器自動產生，並在套用區塊完成後執行。 因為任何用來做為內部區塊一部分的可變變數無法在套用區塊中重新系結，所以產生的轉換保證會是在區塊內的計算 adjoint。 

## <a name="expression-evaluation-statements"></a>運算式評估語句

`Unit` 類型的任何呼叫運算式可以當做語句使用。
這主要是在對傳回 `Unit` 的 qubits 呼叫作業時使用，因為語句的目的是要修改隱含的量子狀態。
運算式評估語句需要結尾的分號。

例如，

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
