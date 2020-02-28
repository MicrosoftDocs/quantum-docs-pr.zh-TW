---
title: 'Q # 作業和函數'
description: '瞭解問 # 作業和函式，以及如何將它們套用在量副程式中。'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907659"
---
# <a name="q-operations-and-functions"></a>Q # 作業和函數

Q # 程式是由一或多個*作業*所組成，其中描述配量作業可以對量子資料進行的副作用，以及一或多個允許修改傳統資料的*函數*。 相對於作業，函數是用來描述純粹的傳統行為，而且除了計算傳統輸出值之外，也不會有任何影響。

在 Q # 中定義的每個作業都可以呼叫任何數目的其他作業，包括語言所定義的內建內建函式作業。 定義這些內部作業的特定方式取決於目的電腦。 在編譯時，每個作業都會表示為可提供給目的電腦的 .NET 類別類型。

## <a name="defining-new-operations"></a>定義新的作業

如上所述，以 Q # 撰寫之配量程式最基本的建立區塊是作業，可以從傳統 .NET 應用程式*呼叫，例如*，使用模擬器，或由 Q # 內的其他作業呼叫。
每個作業都會接受輸入、產生輸出，並指定一或多個作業特製化的執行。
例如，下列作業只會定義預設的本文特製化，並以單一 qubit 作為其輸入，然後在該輸入上呼叫內建的 `X` 作業：

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

關鍵字 `operation` 會開始作業定義，後面接著名稱。在這裡，`BitFlip`。
接下來，輸入的型別會定義為 `Qubit`，以及用來參考新作業內輸入的名稱 `target`。
同樣地，`Unit` 會定義作業的輸出是空的。
這種用法類似于C#和其他命令式語言中的 `void`，而且相當於和其他F#功能性語言中的 `unit`。

> [!NOTE]
> 下面將更詳細地探討此問題，但每個 Q # 中的作業只會接受一個輸入，並只傳回一個輸出。
> 接著會使用*元組*來表示多個輸入和輸出，這會將多個值一起收集成單一值。
> 非正式地說，問 # 是一種「元組輸出」語言。
> 遵循此概念之後，`()` 應該會讀取為「空的」元組，其類型 `Unit`。

在新作業中，如果只需要明確指定預設本文特殊化的執行，就可以在宣告中直接指定實值。 此外，您也可以定義的執行，例如一或多個 `functor` 作業，如下所述。 在上述範例中，唯一的語句是呼叫內建的 Q # 作業 <xref:microsoft.quantum.intrinsic.x>。

作業也會傳回比 `Unit`更有趣的類型。
例如，<xref:microsoft.quantum.intrinsic.m> 作業會傳回 `Result`類型的輸出，表示已執行測量。 我們可以將作業的輸出傳遞至另一個作業，或可以搭配 `let` 關鍵字來定義新的變數。
<!-- Link to UID for superdense conceptual and example documentation. -->
這可代表在較低層級與量子作業互動的傳統計算，例如 superdense 編碼：

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>函子、adjoint 和控制
如果作業會執行單一轉換，則可以定義作業在*adjointed*或*控制*時的運作方式。 作業的 adjoint 特製化會指定它在反向執行時的運作方式，而受控制的特製化則會指定作業在配量暫存器的狀態下套用時的運作方式。
這些特製化的存在可以宣告為作業簽章的一部分：在下列範例中 `is Adj + Ctl`。 然後編譯器會產生每個這類隱含宣告特製化的對應執行。 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Q # 中的許多作業都代表單一閘道。
> 如果 $U $ 是由作業 `U`表示的單一閘道，則 `Adjoint U` 代表單一閘道 $U ^ \dagger $。

如果編譯器無法產生執行，則可以明確指定。 這類明確特製化宣告可以包含適當的世代指示詞或使用者定義的實作為。 範例中 `PrepareEntangledPair` 的程式碼相當於下列程式碼，其中包含明確的特製化宣告： 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
關鍵字 `auto` 表示編譯器應該決定如何產生特製化執行。
如果編譯器無法自動產生特定特製化的實作為，或者可以指定更有效率的執行，則也可以手動定義執行。

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
在上述範例中，`adjoint invert;` 指出 adjoint 特製化是藉由將主體實作為反轉而產生，`controlled adjoint invert;` 表示會藉由反轉受控制特製化的指定實作為來產生受控制的 adjoint 特製化。

我們會在[更高順序的控制流程](xref:microsoft.quantum.concepts.control-flow)中看到更多的範例。

若要呼叫作業的特製化，請使用 `Adjoint` 或 `Controlled` 關鍵字。
例如，您可以使用 adjoint `PrepareEntangledPair` 將光子狀態轉換回 unentangled 組 qubits，以撰寫更簡潔地的上述 superdense 程式碼範例：

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

設計要與函子搭配使用的作業時，有一些重要的限制需要考慮。
最重要的是，使用任何其他作業的輸出值之作業的特製化，不能由編譯器自動產生，因為在這類作業中重新排序語句以取得相同的效果並不明確。


## <a name="defining-new-functions"></a>定義新函數

問 # 也允許定義函式，這與作業*不同，因為*它們不允許超出計算輸出值的任何效果。
特別是，函式無法呼叫作業、對 qubits 採取動作、取樣亂數，或以其他方式相依于函式的輸入值以外的狀態。
因此，Q # 函式是*單純*的，因為它們一律會將相同的輸入值對應到相同的輸出值。
這可讓 Q # 編譯器在產生作業特製化時，安全地重新排序呼叫函式的方式和時機。

定義函式的運作方式類似于定義作業，不同之處在于無法為函式定義任何 adjoint 或受控特殊化。
例如：

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
只要能夠這麼做，就能以函式而非作業的形式寫出傳統邏輯，這會很有説明，可以更輕鬆地從作業中使用。
例如，如果我們以作業撰寫 `Square`，則編譯器無法保證以相同的輸入呼叫它會一致地產生相同的輸出。

若要以底線表示函式和作業之間的差異，請考慮傳統方式從 Q # 操作中取樣亂數字的問題：

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

每次呼叫 `U` 時，它在 `target`上會有不同的動作。
特別的是，編譯器無法保證如果我們將 `adjoint auto` 特製化宣告加入 `U`，`U(target); Adjoint U(target);` 會做為身分識別（也就是不需要 op）。
這會違反我們在[向量和矩陣](xref:microsoft.quantum.concepts.vectors)中看到的 adjoint 定義，讓能夠在我們呼叫作業的作業中自動產生 adjoint 特製化，<xref:microsoft.quantum.math.randomreal> 會中斷編譯器所提供的保證;<xref:microsoft.quantum.math.randomreal> 是不存在 adjoint 或控制版本的作業。

另一方面，允許 `Square` 之類的函式呼叫是安全的，因為編譯器可以確保它只需要保留 `Square` 的輸入，才能保持其輸出穩定。
因此，將盡可能多的傳統邏輯隔離到函式，可讓您輕鬆地在其他函數和作業中重複使用該邏輯。

## <a name="control-flow"></a>控制流程

在作業或函式內，每個語句會依序執行，類似于最常見的命令式傳統語言。
不過，您可以透過三種不同的方式修改這個控制流程：

- `if` 語句
- `for` 迴圈
- `repeat`-`until` 迴圈

我們會在討論[重複直到成功（ru）](xref:microsoft.quantum.techniques.qubits#measurements)線路之前，延遲對後者的討論。
不過，`if` 和 `for` 控制流程結構，對於大部分的傳統程式設計語言而言，都是以熟悉的方式進行。
特別是，`if` 語句可以接受條件，後面可能接著一個或多個 `elif` 語句，而且可能以 `else`結尾：

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

同樣地，`for` 迴圈表示在整數範圍或陣列元素上的反復專案：

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

重要的是，`for` 迴圈和 `if` 語句甚至可以用於自動產生特殊化的作業中。 在此情況下，`for` 迴圈的 adjoint 會反轉方向，並接受每個反復專案的 adjoint。
這會遵循「鞋與 socks」原則：如果您想要復原並加上「鞋」，您必須先復原鞋，然後再復原「socks」。
如果您還在戴鞋，也能讓您更輕鬆地嘗試並將您的 socks 轉成由於！

## <a name="operations-and-functions-as-first-class-values"></a>作為第一級值的作業和函式

使用函式而不是作業來推理控制流程和傳統邏輯的一項重要技巧，就是利用 Q # 中的作業和函*式是第一類*。
也就是說，它們是語言中的每個值本身的許可權。
例如，下列是完全有效的 Q # 程式碼，如果有一點間接：

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

上述程式碼片段中的變數 `ourH` 值就是作業 <xref:microsoft.quantum.intrinsic.h>，因此我們可以像任何其他作業一樣呼叫該值。
這可讓我們撰寫在其輸入過程中採取作業的作業，形成更高順序的控制流程概念。
比方說，我們可以想像一下，將作業套用到相同的目標 qubit 兩次，以「正方形」作業。

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

在此範例中，出現在類型 `(Qubit => Unit)` 中的 `=>` 箭號表示輸入欄位 `op` 是做為其輸入類型 `Qubit` 的作業，並產生空的元組做為其輸出。
此外，我們還指定該作業類型的特性，其中包含支援哪些函子的相關資訊。
`(Qubit => Unit)` 類型的作業不支援 `Adjoint` 或 `Controlled` 仿函數。 如果我們想要指出該類型的作業必須支援（例如 `Adjoint` 仿函數），我們必須將它宣告為 adjointable。 這是藉由使用注釋 `is Adj` 至類型來完成。 同樣地，`(Qubit => Unit is Ctl)` 表示該類型的作業支援 `Controlled` 仿函數。 我們會在我們進一步討論[Q # 中的類型](xref:microsoft.quantum.language.type-model)時進一步探討。

現在，我們強調，我們也可以將作業當做輸出的一部分傳回，讓我們可以將一些傳統條件式邏輯隔離為傳統函式，以作業的形式傳回量副程式的描述。
做為簡單的範例，請考慮 teleportation 範例，其中接收兩個傳統訊息的合作物件需要使用訊息，將其 qubit 解碼為適當的傳送狀態。
我們可以根據採用這兩個傳統位的函式撰寫此程式，並傳回適當的解碼作業。

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

這個新函式確實是一個函式，在此情況下，如果我們使用相同的 `hereBit` 和 `thereBit`值來呼叫它，我們一律會取回相同的作業。
因此，可以安全地在作業內執行此解碼器，而不需考慮解碼邏輯如何與不同作業特製化的定義互動。
也就是，我們已將傳統邏輯隔離在函式內，並保證編譯器，只要保留輸入，函式呼叫就可以與 impunity 重新排序。

我們也可以將函式視為第一類的值，因為我們會在討論[作業和](#operations-and-functions-as-first-class-values)函式類型時更詳細地看到。

## <a name="partially-applying-operations-and-functions"></a>部分套用作業和函式

我們可以透過使用*部分應用程式*來傳回作業的函式執行更多動作，我們可以將輸入的一個或多個部分提供給函式或作業，而不需要實際呼叫它。 例如，若要重新叫用上述的 `ApplyTwice` 範例，我們可以指出我們不想要對應套用輸入作業的 qubit 指定：

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

在此情況下，本機變數 `twiceOp` 保留部分套用的作業 `ApplyTwice(op, _)`，其中尚未指定的輸入部分會以 `_`表示。
當我們實際在下一行呼叫 `twiceOp` 時，我們會將輸入的所有剩餘部分當做原始作業傳遞給部分套用的作業。
因此，上述程式碼片段與直接呼叫 `ApplyTwice(op, target)` 相同，因此我們引進了新的區域變數，讓我們能夠延遲呼叫，同時提供輸入的某些部分。

由於已部分套用的作業並不會實際被呼叫，直到提供了完整的輸入為止，我們也可以安全地從函式內部分套用作業。

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

就原則而言，`SquareOperation` 中的傳統邏輯可能更牽涉到，但它仍會與作業的其餘部分隔離，因為編譯器可以提供關於函數的保證。
這種方法會在整個 Q # 標準程式庫中用來以可在量副程式中輕鬆使用的方式來表示傳統控制流程。
