---
title: 使用 Q# 探索纏結
description: 了解如何以 Q# 撰寫量子程式。 使用 Quantum Development Kit (QDK) 開發貝爾狀態應用程式
author: natke
ms.author: nakersha
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 271eb7f496835f152573be930d0fe24e59f2d15d
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630082"
---
# <a name="tutorial-explore-entanglement-with-q"></a>教學課程：使用 Q\# 探索糾纏

在本教學課程中，我們會示範如何撰寫 Q# 程式來操控和測量量子位元，並示範疊加和糾纏的效果，
從而引導您安裝 QDK、建立程式，並在量子模擬器上執行該程式。  

您將會撰寫一個名為 Bell 的應用程式以示範量子纏結。
Bell 這個名稱取自「貝爾狀態」，是指兩個量子位元的特定狀態，用來代表疊加和量子纏結的最簡單範例。

## <a name="prerequisites"></a>必要條件

如果您已準備好要開始撰寫程式碼，請先遵循下列步驟再繼續進行： 

* 安裝適用於 [Python](xref:microsoft.quantum.install.python) 或 [.NET](xref:microsoft.quantum.install.cs) 的 Quantum 開發套件。
* 如果您已安裝 QDK，請確定您已[更新](xref:microsoft.quantum.update)為最新版本

您也可以在不安裝 QDK 的情況下繼續閱讀本文內容，以了解 Q# 程式設計語言和量子運算的首要概念。

## <a name="demonstrating-qubit-behavior-with-q"></a>使用 Q# 示範量子位元行為

回想一下我們簡單的[量子位元定義](xref:microsoft.quantum.overview.understanding)。  其中，古典位元會有單一二進位值，例如 0 或 1，而[量子位元](xref:microsoft.quantum.glossary#qubit)的狀態則可以是 0 和 1 的**疊加**。  在概念上，可以將量子位元想成空間中的方向 (又稱為向量)。  量子位元可以是任何可能方向的其中一個。 兩個**古典狀態**是兩個方向，分別代表 100% 測量到 0 的機率和 100% 測量到 1 的機率。  這種表示法也能以[布洛赫球體](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)更正式地視覺化。

測量動作會產生二進位結果，並變更量子位元狀態。 測量會產生一個二進位值，也就是 0 或 1。  量子位元會從疊加狀態 (任何方向) 變為兩個古典狀態的其中一個。  之後，在沒有任何干擾作業的情況下重複相同的測量，會產生相同的二進位結果。  

多個量子位元可以[**纏結**](xref:microsoft.quantum.glossary#entanglement)。 當我們測量一個纏結的量子位元時，對其他量子位元狀態的了解也會隨之更新。

現在，我們已準備好要來示範如何用 Q# 表示此行為。  您將從最簡單的程式著手建置，以示範量子疊加和量子纏結。

## <a name="setup"></a>安裝程式

本教學課程使用主機程式，並由兩個部分組成：

1. 一系列的量子演算法，使用 Q# 量子程式設計語言來實作。
1. 一個主機程式，以作為主要進入點，並叫用 Q# 作業以執行量子演算法來實作，例如 Python 或 C#。

#### <a name="python"></a>[Python](#tab/tabid-python)

1. 選擇應用程式的位置

1. 建立名為 `Bell.qs`的檔案。 此檔案會包含您的 Q# 程式碼。

1. 建立名為 `host.py`的檔案。 此檔案會包含您的 Python 主機程式碼。

#### <a name="c-command-line"></a>[C# 命令列](#tab/tabid-csharp)

1. 建立新的 Q# 專案：

    ```
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    您應該會看到 `.csproj` 檔案、名為 `Operations.qs` 的 Q# 檔案，以及名為 `Driver.cs` 的主機程式檔案

1. 重新命名 Q# 檔案

    ```
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. 建立新專案

   * 開啟 Visual Studio
   * 移至 [檔案] 功能表，然後選取 [新增] -> [專案...]
   * 在專案範本總管的搜尋欄位中輸入 `Q#`，然後選取 `Q# Application` 範本
   * 將您的專案命名為 `Bell`

1. 重新命名 Q# 檔案

   * 瀏覽至 [方案總管]
   * 以滑鼠右鍵按一下 `Operations.qs` 檔案
   * 將其重新命名為 `Bell.qs`

* * *

## <a name="write-a-q-operation"></a>撰寫 Q# 作業

我們的目標是要準備兩個特定量子狀態的量子位元，示範如何利用 Q# 來操作量子位元以變更其狀態，並示範疊加和纏結的效果。 我們會逐一加以建置，來示範量子位元的狀態、操作和測量。

**概觀：** 在下列的第一個程式碼中，我們會示範如何在 Q# 中處理量子位元。  我們會引進 `M` 和 `X` 兩項作業來轉換量子位元的狀態。 

在此程式碼片段中定義的 `Set` 作業需要一個量子位元做為參數和另一個參數 `desired`，後者代表我們想要的量子位元狀態。  `Set` 作業使用 `M` 作業對量子位元執行測量。  在 Q # 中，量子位元的測量一律會傳回 `Zero` 或 `One`。  如果測量傳回的值不等於想要的值，Set 會「翻轉」量子位元；意思是說，它會執行 `X` 作業，將量子位元的狀態變更為新的狀態，而新狀態下測量傳回 `Zero` 和 `One` 的機率會相反。  為了示範 `Set` 作業的效果，於是加入 `TestBellState` 作業。  這項作業需要一個 `Zero` 或 `One` 的輸入，並使用該輸入來呼叫 `Set` 作業數次，然後計算從量子位元測量傳回 `Zero` 的次數，以及傳回 `One` 的次數。 當然，在第一次模擬 `TestBellState` 作業時，我們預期輸出會顯示以 `Zero` 作為輸入參數之量子位元的所有測量都會傳回 `Zero`，而以 `One` 作為輸入參數之量子位元的所有測量都會傳回 `One`。  接下來，我們會在 `TestBellState` 加入更多程式碼來示範疊加和纏結。


### <a name="q-operation-code"></a>Q# 作業程式碼

1. 將 Bell.qs 檔案的內容取代為下列程式碼：

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    現在已經可以呼叫這項作業來將量子位元設定為古典狀態，亦即 100% 的時間會傳回 `Zero` 或 100% 的時間會傳回 `One`。  `Zero` 和 `One` 是常數，代表測量量子位元的唯二兩個可能結果。

    `Set` 作業會測量量子位元。
    如果量子位元是我們想要的狀態 `Set`，就不動它；反之，則執行 `X` 作業，將量子位元的狀態變更為想要的狀態。

### <a name="about-q-operations"></a>關於 Q# 作業

Q# 作業是量子副程式。 也就是說，它是包含量子作業的可呼叫常式。

作業的引數會在括弧內指定為元組。

作業的傳回類型指定於冒號後面。 在此案例中，`Set` 作業不會傳回任何項目，因此會標示為傳回 `Unit`。 此 Q# 項目等同於 F# 中的 `unit`，且大致上類似於 C# 中的 `void`，以及 Python 中的空元組 (`Tuple[()]`)。

您在第一個 Q# 作業中使用了兩個量子作業：

* [M](xref:microsoft.quantum.intrinsic.m) 作業，會測量量子位元的狀態
* [X](xref:microsoft.quantum.intrinsic.x) 作業，會翻轉量子位元的狀態

量子作業會轉換量子位元的狀態。 有時候會看到「量子閘」這個較接近古典邏輯閘的詞而不是作業。 這源自於量子運算初期，當時的演算法只是理論架構，是用類似古典運算中的電路圖來做出圖表化的視覺呈現。

### <a name="add-q-test-code"></a>新增 Q# 測試程式碼

1. 在 `Bell.qs` 檔案中，將下列作業新增至命名空間內的 `Set` 作業後面：

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    此作業 (`TestBellState`) 會迴圈進行 `count` 次反覆運算、設定量子位元的指定 `initial` 值，然後測量 (`M`) 結果。 它會收集關於我們測量了多少個零和一的統計資料，並將其傳回給呼叫端。 它會執行另一項必要的作業。 它會先將量子位元重設為已知狀態 (`Zero`) 再加以傳回，讓其他人可將此量子位元配置於已知狀態中。 這是 `using` 陳述式所需的條件。

### <a name="about-variables-in-q"></a>關於 Q# 中的變數

根據預設，Q# 中的變數是不可變的；其值在繫結之後即無法變更。 `let` 關鍵字可用來指出不可變變數的繫結。 作業引數一律為不可變的。

如果您需要可變更值的變數 (例如範例中的 `numOnes`)，您可以使用 `mutable` 關鍵字來宣告變數。 可變變數的值可使用 `set` 陳述式來變更。

在這兩種情況下，都會由編譯器來推斷變數的類型。 Q# 的變數不需要任何類型註解。

### <a name="about-using-statements-in-q"></a>關於 Q# 中的 `using` 陳述式

在 Q# 中，`using` 陳述式也很特別。 它會用來配置要用於程式碼區塊中的量子位元。 在 Q # 中，所有量子位元都是動態配置和釋出的，而不是在複雜演算法的整個存留期內都存在的固定資源。 `using` 陳述式會在一開始配置一組量子位元，並在區塊結尾處釋出這些量子位元。

## <a name="create-the-host-application-code"></a>建立主應用程式的程式碼

#### <a name="python"></a>[Python](#tab/tabid-python)

1. 開啟 `host.py` 檔案並新增下列程式碼：

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. 將 `Driver.cs` 檔案的內容取代為下列程式碼：

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>關於主應用程式的程式碼

#### <a name="python"></a>[Python](#tab/tabid-python)

Python 主應用程式有三個部分：

* 計算量子演算法所需的任何引數。 在此範例中，`count` 是固定為 1000，而 `initial` 是量子位元的初始值。
* 呼叫已匯入之 Q# 作業的 `simulate()` 方法，以執行量子演算法。
* 處理作業的結果。 在範例中，`res` 會接收作業的結果。 此處的結果是模擬器所測量的零數目 (`num_zeros`) 和一數目 (`num_ones`) 的元組。 我們會解構元組以取得這兩個欄位，並列印結果。

#### <a name="c"></a>[C#](#tab/tabid-csharp)

C# 主應用程式有四個部分：

* 建構量子模擬器。 範例中的模擬器為 `qsim`。
* 計算量子演算法所需的任何引數。 在此範例中，`count` 是固定為 1000，而 `initial` 是量子位元的初始值。
* 執行量子演算法。 每個 Q# 作業都會產生一個具有相同名稱的 C# 類別。 此類別具有 `Run` 方法，會以**非同步方式**執行作業。 執行是非同步的，因為實際硬體的執行將是非同步的。 由於 `Run` 方法是非同步的，因此我們會擷取 `Result` 屬性；這將會封鎖執行，直到工作完成並同步傳回結果。
* 處理作業的結果。 在範例中，`res` 會接收作業的結果。 此處的結果是模擬器所測量的零數目 (`numZeros`) 和一數目 (`numOnes`) 的元組。 在 C# 中，這會以的 ValueTuple 的形式傳回。 我們會解構元組以取得這兩個欄位，並列印結果，然後等待按鍵。

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>建置和執行

#### <a name="python"></a>[Python](#tab/tabid-python)

1. 在您的終端機上執行下列命令：

    ```
    python host.py
    ```

    此命令會執行主應用程式，以模擬 Q# 作業。

結果應為：

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[命令列/Visual Studio Code](#tab/tabid-csharp)

1. 在您的終端機上執行下列命令：

    ```dotnetcli
    dotnet run
    ```

    此命令會自動下載所有必要套件、建置應用程式，然後在命令列上加以執行。

1. 或者，按 **F1** 開啟命令選擇區，然後選取 **[偵錯：啟動但不偵錯]** 。
系統可能會提示您建立新的 ``launch.json`` 檔案以說明如何啟動程式。
預設的 ``launch.json`` 應可適用於大部分的應用程式。

結果應為：

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. 只要按 `F5`，您的程式應該就會建置並執行！

結果應為：

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

當您按下按鍵後，程式就會結束。

* * *

## <a name="prepare-superposition"></a>準備疊加

**概觀** 現在讓我們來看一下 Q# 如何表示疊加狀態的量子位元。  前面說過，量子位元的狀態可以是 0 和 1 的疊加。  我們將使用 `Hadamard` 作業來達成此狀態。 如果量子位元是在其中一個古典狀態 (其測量會傳回一律 `Zero` 或一律 `One` )，則 `Hadamard` 或 `H` 作業會將量子位元置於一種「量子位元測量結果 50% 的時間會傳回 `Zero`、50% 的時間會傳回 `One`」的狀態。  概念上可以將量子位元想成介於 `Zero` 和 `One` 之間。  現在，當我們模擬 `TestBellState` 作業時，會看到在測量之後，結果傳回 `Zero` 和 `One` 的次數大致相同。  

首先，我們將嘗試翻轉量子位元 (如果量子位元處於 `Zero` 狀態，會翻轉成 `One`，反之亦然)。 在 `TestBellState` 中加以測量之前先執行 `X` 作業，即可完成此動作：

```qsharp
X(qubit);
let res = M(qubit);
```

此時，結果 (按下 `F5` 之後) 將會反轉：

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

不過，我們到目前為止所看到的一切都是傳統的。 我們要取得量子結果。 我們只需要將先前執行中的 `X` 作業取代為 `H` 或 Hadamard 作業即可。 我們不會將量子位元從 0 一路翻轉到 1，而是只會翻轉一半。 `TestBellState` 中取代的行此時會顯示如下：

```qsharp
H(qubit);
let res = M(qubit);
```

現在，結果會更有趣：

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

每次測量時，我們都會要求一個傳統值，但量子位元介於 0 到 1 的中間，因此我們 (在統計上) 有一半時間會取得 0，一半的時間會取得 1。 這就是所謂的__疊加__，它讓我們首次得以實際檢視量子狀態。

## <a name="prepare-entanglement"></a>準備糾纏

**概觀：** 現在讓我們來看一下 Q# 如何表示量子位元纏結。  首先，我們將第一個量子位元設定為初始狀態，然後使用 `H` 作業將它置於疊加狀態。  然後，在測量第一個量子位元之前，我們使用新的作業 (`CNOT`)，代表 Controlled-Not。  對兩個量子位元執行這項作業的結果是：如果第一個量子位元是 `One` 就會翻轉第二個量子位元。  現在，這兩個量子位元相互纏結。  第一個量子位元的統計資料並未變更 (測量後 `Zero` 或 `One` 的機率各半)，但現在當我們測量第二個量子位元時，其量值「一律」會與第一個量子位元的相同。 我們的 `CNOT` 讓這兩個量子位元相互糾纏，因此其中一個量子位元發生的情況，也會出現在另一個量子位元上。 如果您反轉測量 (先執行第二個量子位元，再執行第一個)，也會發生相同的情況。 第一個測量是隨機的，第二個測量則會根據第一個測量所發現的結果，以鎖定步驟執行。

首先我們必須做的是配置 2 個量子位元，而不是 `TestBellState` 中的一個：

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

這可讓我們先新增作業 (`CNOT`)，再於 `TestBellState` 中測量 (`M`)：

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

我們已新增另一項 `Set` 作業來初始化第一個量子位元，以確保它在作業開始後一律會處於 `Zero` 狀態。

在加以釋出之前，我們也需要先重設第二個量子位元。

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

完整的常式此時會顯示如下：

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
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
                Set(initial, q0);
                Set(Zero, q1);

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
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

新的傳回值 (`agree`) 會追蹤第一個量子位元的測量與第二個量子位元的測量是否相符。 我們也必須據以更新主應用程式：

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

執行完成後，會產生讓人眼睛為之一亮的結果：

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

如之前在概觀所述，第一個量子位元的統計資料並未變更 (0 或 1 的機率各半)，但現在當我們測量第二個量子位元時，其量值__一律__會與第一個量子位元的相同，因為它們相互纏結!

恭喜，您已撰寫了第一個量子程式！

## <a name="next-steps"></a>後續步驟

[格羅弗搜尋](xref:microsoft.quantum.quickstarts.search)教學課程會示範如何建立和執行格羅弗搜尋 (最受歡迎的量子運算演算法之一)，並提供 Q# 程式的絕佳範例，可用來解決量子運算的實際問題。  

[開始使用量子開發工具組](xref:microsoft.quantum.welcome)中建議更多學習 Q# 和量子程式設計的方式。
