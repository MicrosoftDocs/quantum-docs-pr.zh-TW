---
title: 使用 Q# 探索纏結
description: 了解如何以 Q# 撰寫量子程式。 使用 Quantum Development Kit (QDK) 開發貝爾狀態應用程式
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 16c93b3dd17363c06602529cb34e8fc84aadc7a8
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415417"
---
# <a name="tutorial-explore-entanglement-with-q"></a>教學課程：使用 Q\# 探索糾纏

在本教學課程中，我們會示範如何撰寫 Q# 程式來操控和測量量子位元，並示範疊加和糾纏的效果，

您將會撰寫一個名為 Bell 的應用程式以示範量子纏結。
Bell 這個名稱取自「貝爾狀態」，是指兩個量子位元的特定狀態，用來代表疊加和量子纏結的最簡單範例。

## <a name="pre-requisites"></a>必要條件

如果您已準備好要開始撰寫程式碼，請先遵循下列步驟再繼續進行： 

* 使用您慣用的語言和開發環境來[安裝](xref:microsoft.quantum.install)配量開發工具組。
* 如果您已安裝 QDK，請確定您已[更新](xref:microsoft.quantum.update)為最新版本

您也可以遵循敘述，而不需要安裝 QDK、查看問 # 程式設計語言的總覽，以及量子運算的第一個概念。

## <a name="in-this-tutorial-youll-learn-how-to"></a>在本教學課程中，您將了解如何：

> [!div class="checklist"]
> * 在 Q 中建立和合併作業\#
> * 建立作業以將 qubits 放在重迭、entangle 並加以測量。
> * 示範在模擬器中執行 Q # 程式的量子會任何牽連。 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>使用 QDK 示範 qubit 行為

其中，古典位元會有單一二進位值，例如 0 或 1，而[量子位元](xref:microsoft.quantum.glossary#qubit)的狀態則可以是 0 和 1 的**疊加**。  就概念而言，qubit 的狀態可以視為抽象空間（也稱為向量）中的方向。  Qubit 狀態可以是任何可能的方向。 兩個**古典狀態**是兩個方向，分別代表 100% 測量到 0 的機率和 100% 測量到 1 的機率。

測量動作會產生二進位結果，並變更量子位元狀態。
測量會產生一個二進位值，也就是0或1。  量子位元會從疊加狀態 (任何方向) 變為兩個古典狀態的其中一個。  之後，在沒有任何干擾作業的情況下重複相同的測量，會產生相同的二進位結果。  

多個量子位元可以[**纏結**](xref:microsoft.quantum.glossary#entanglement)。  當我們測量一個纏結的量子位元時，對其他量子位元狀態的了解也會隨之更新。

現在，我們已準備好要來示範如何用 Q# 表示此行為。  您將從最簡單的程式著手建置，以示範量子疊加和量子纏結。

## <a name="creating-a-q-project"></a>建立 Q # 專案

首先我們要建立一個新的 Q # 專案。 在本教學課程中，我們將使用以 VS Code 的[命令列應用程式](xref:microsoft.quantum.install.standalone)為基礎的環境。

若要建立新的專案，請在 VS Code： 

1. 按一下 [**視圖**] [命令選擇區]  ->  **Command Palette** ，然後選取 [ **Q #：建立新專案**]。
2. 按一下 [**獨立主控台應用程式**]。
3. 流覽至要儲存專案的位置，然後按一下 [**建立專案**]。
4. 成功建立專案後，按一下右下方的 [**開啟新專案**]。

在此情況下，我們稱之為專案 `Bell` 。 這會產生兩個檔案： `Bell.csproj` 、專案檔，以及 `Program.qs` 用來撰寫應用程式的 Q # 應用程式範本。 的內容 `Program.qs` 應該是：

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>撰寫 Q \# 應用程式
 
我們的目標是要準備兩個特定量子狀態的量子位元，示範如何利用 Q# 來操作量子位元以變更其狀態，並示範疊加和纏結的效果。 我們會逐一建立這段程式，以引進 qubit 狀態、作業和測量。

### <a name="initialize-qubit-using-measurement"></a>使用測量來初始化 qubit

在下列的第一個程式碼中，我們會示範如何在 Q# 中處理量子位元。  我們會介紹兩項作業， [`M`](xref:microsoft.quantum.intrinsic.m) 並 [`X`](xref:microsoft.quantum.intrinsic.x) 轉換 qubit 的狀態。 在此程式碼片段中定義的 `SetQubitState` 作業需要一個量子位元做為參數和另一個參數 `desired`，後者代表我們想要的量子位元狀態。  `SetQubitState` 作業使用 `M` 作業對量子位元執行測量。  在 Q # 中，qubit 量值一律會傳回 `Zero` 或 `One` 。  如果測量傳回的值不等於所需的值，就 `SetQubitState` 會「翻轉」 qubit; 也就是說，它會執行作業 `X` ，這會將 qubit 狀態變更為新狀態，其中測量傳回和的機率 `Zero` `One` 會反轉。 如此一來，一律會將 `SetQubitState` 目標 qubit 置於所需的狀態。

將的內容取代 `Program.qs` 為下列程式碼：


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

現在已經可以呼叫這項作業來將量子位元設定為古典狀態，亦即 100% 的時間會傳回 `Zero` 或 100% 的時間會傳回 `One`。
`Zero` 和 `One` 是常數，代表測量量子位元的唯二兩個可能結果。

`SetQubitState` 作業會測量量子位元。 如果量子位元是我們想要的狀態 `SetQubitState`，就不動它；反之，則執行 `X` 作業，將量子位元的狀態變更為想要的狀態。

#### <a name="about-q-operations"></a>關於 Q# 作業

Q# 作業是量子副程式。 也就是說，它是可呼叫的常式，其中包含對其他量子作業的呼叫。

作業的引數會在括弧內指定為元組。

作業的傳回類型指定於冒號後面。 在此案例中，`SetQubitState` 作業不會傳回任何項目，因此會標示為傳回 `Unit`。 此 Q# 項目等同於 F# 中的 `unit`，且大致上類似於 C# 中的 `void`，以及 Python 中的空元組 (`Tuple[()]`)。

您在第一個 Q# 作業中使用了兩個量子作業：

* [`M`](xref:microsoft.quantum.intrinsic.m)運算，可測量 qubit 的狀態。
* 作業，此作業會 [`X`](xref:microsoft.quantum.intrinsic.x) 翻轉 qubit 的狀態。

量子作業會轉換量子位元的狀態。 有時候會看到「量子閘」這個較接近古典邏輯閘的詞而不是作業。 這源自於量子運算初期，當時的演算法只是理論架構，是用類似古典運算中的電路圖來做出圖表化的視覺呈現。

### <a name="counting-measurement-outcomes"></a>計算測量結果

為了示範 `SetQubitState` 作業的效果，於是加入 `TestBellState` 作業。 這項作業需要一個 `Zero` 或 `One` 的輸入，並使用該輸入來呼叫 `SetQubitState` 作業數次，然後計算從量子位元測量傳回 `Zero` 的次數，以及傳回 `One` 的次數。 當然，在第一次模擬 `TestBellState` 作業時，我們預期輸出會顯示以 `Zero` 作為輸入參數之量子位元的所有測量都會傳回 `Zero`，而以 `One` 作為輸入參數之量子位元的所有測量都會傳回 `One`。 此外，我們會在中新增程式碼， `TestBellState` 以示範重迭和會任何牽連。

在 `Bell.qs` 檔案中，將下列作業新增至命名空間內的 `SetQubitState` 作業後面：

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
請注意，我們已在之前新增一行， `return` 以使用函式（ `Message` ） [microsoft 量子. message] 在主控台中列印說明訊息

此作業 (`TestBellState`) 會迴圈進行 `count` 次反覆運算、設定量子位元的指定 `initial` 值，然後測量 (`M`) 結果。 它會收集關於我們測量了多少個零和一的統計資料，並將其傳回給呼叫端。 它會執行另一項必要的作業。 它會先將量子位元重設為已知狀態 (`Zero`) 再加以傳回，讓其他人可將此量子位元配置於已知狀態中。 這是 `using` 陳述式所需的條件。

#### <a name="about-variables-in-q"></a>關於 Q 中的變數\#

根據預設，Q# 中的變數是不可變的；其值在繫結之後即無法變更。 `let` 關鍵字可用來指出不可變變數的繫結。 作業引數一律為不可變的。

如果您需要可變更值的變數 (例如範例中的 `numOnes`)，您可以使用 `mutable` 關鍵字來宣告變數。 可變變數的值可使用 `setQubitState` 陳述式來變更。

在這兩種情況下，都會由編譯器來推斷變數的類型。 Q# 的變數不需要任何類型註解。

#### <a name="about-using-statements-in-q"></a>關於 `using` Q 中的語句\#

在 Q# 中，`using` 陳述式也很特別。 它會用來配置要用於程式碼區塊中的量子位元。 在 Q # 中，所有量子位元都是動態配置和釋出的，而不是在複雜演算法的整個存留期內都存在的固定資源。 `using` 陳述式會在一開始配置一組量子位元，並在區塊結尾處釋出這些量子位元。

## <a name="execute-the-code-from-the-command-line"></a>從命令列執行程式碼

若要執行程式碼，我們必須指定在提供命令*時可呼叫執行的編譯器* `dotnet run` 。 這項作業的完成方式是在 Q # 檔案中進行簡單的變更，方法是 `@EntryPoint()` `TestBellState` 在此情況下，直接在可呼叫：作業的前面加入一行。 完整的程式碼應該是：

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

若要執行程式，我們需要 `count` `initial` 從命令列指定和引數。 讓我們選擇例如 `count = 1000` 和 `initial = One` 。 輸入下列命令：

```dotnetcli
dotnet run --count 1000 --initial One
```

而且您應該觀察下列輸出：

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

如果您嘗試使用 `initial = Zero` ，您應該會看到：

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>準備疊加

現在讓我們來看一下 Q # 如何表示將 qubits 放在重迭中的方式。  前面說過，量子位元的狀態可以是 0 和 1 的疊加。  我們將使用 `Hadamard` 作業來達成此狀態。 如果量子位元是在其中一個古典狀態 (其測量會傳回一律 `Zero` 或一律 `One` )，則 `Hadamard` 或 `H` 作業會將量子位元置於一種「量子位元測量結果 50% 的時間會傳回 `Zero`、50% 的時間會傳回 `One`」的狀態。  概念上可以將量子位元想成介於 `Zero` 和 `One` 之間。  現在，當我們模擬 `TestBellState` 作業時，會看到在測量之後，結果傳回 `Zero` 和 `One` 的次數大致相同。  

### <a name="x-flips-qubit-state"></a>`X`翻轉 qubit 狀態

首先，我們將嘗試翻轉量子位元 (如果量子位元處於 `Zero` 狀態，會翻轉成 `One`，反之亦然)。 在 `TestBellState` 中加以測量之前先執行 `X` 作業，即可完成此動作：

```qsharp
X(qubit);
let res = M(qubit);
```

現在會反轉結果：

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

現在讓我們來探索 qubits 的量子屬性。

### <a name="h-prepares-superposition"></a>`H`準備重迭

我們只需要將先前執行中的 `X` 作業取代為 `H` 或 Hadamard 作業即可。 我們不會將量子位元從 0 一路翻轉到 1，而是只會翻轉一半。 `TestBellState` 中取代的行此時會顯示如下：

```qsharp
H(qubit);
let res = M(qubit);
```

現在，結果會更有趣：

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

每次測量時，我們都會要求一個傳統值，但量子位元介於 0 到 1 的中間，因此我們 (在統計上) 有一半時間會取得 0，一半的時間會取得 1。
這就是所謂的**疊加**，它讓我們首次得以實際檢視量子狀態。

## <a name="prepare-entanglement"></a>準備糾纏

現在讓我們來看一下 Q# 如何表示量子位元纏結。
首先，我們將第一個量子位元設定為初始狀態，然後使用 `H` 作業將它置於疊加狀態。  然後，在測量第一個 qubit 之前，我們會使用新的作業（ `CNOT` ），這代表受控制的 NOT。  對兩個量子位元執行這項作業的結果是：如果第一個量子位元是 `One` 就會翻轉第二個量子位元。  現在，這兩個量子位元相互纏結。  第一個量子位元的統計資料並未變更 (測量後 `Zero` 或 `One` 的機率各半)，但現在當我們測量第二個量子位元時，其量值「一律」會與第一個量子位元的相同。 我們的 `CNOT` 讓這兩個量子位元相互糾纏，因此其中一個量子位元發生的情況，也會出現在另一個量子位元上。 如果您反轉測量 (先執行第二個量子位元，再執行第一個)，也會發生相同的情況。 第一個測量是隨機的，第二個測量則會根據第一個測量所發現的結果，以鎖定步驟執行。

我們要做的第一件事是配置兩個 qubits，而不是中的一個 `TestBellState` ：

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

這可讓我們先新增作業 (`CNOT`)，再於 `TestBellState` 中測量 (`M`)：

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

我們已新增另一項 `SetQubitState` 作業來初始化第一個量子位元，以確保它在作業開始後一律會處於 `Zero` 狀態。

在加以釋出之前，我們也需要先重設第二個量子位元。

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

完整的常式此時會顯示如下：

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

如果加以執行，我們會得到與之前相同機率各半的結果。 不過，我們想知道的是第二個量子位元對第一個測量的量子位元有何反應。 我們會使用新版本的 `TestBellState` 作業來新增此統計資料：

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

新的傳回值 (`agree`) 會追蹤第一個量子位元的測量與第二個量子位元的測量是否相符。

執行我們取得的程式碼：

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

如之前在概觀所述，第一個量子位元的統計資料並未變更 (0 或 1 的機率各半)，但現在當我們測量第二個量子位元時，其量值__一律__會與第一個量子位元的相同，因為它們相互纏結!

## <a name="next-steps"></a>後續步驟

[格羅弗搜尋](xref:microsoft.quantum.quickstarts.search)教學課程會示範如何建立和執行格羅弗搜尋 (最受歡迎的量子運算演算法之一)，並提供 Q# 程式的絕佳範例，可用來解決量子運算的實際問題。  

[開始使用量子開發工具組](xref:microsoft.quantum.welcome)中建議更多學習 Q# 和量子程式設計的方式。