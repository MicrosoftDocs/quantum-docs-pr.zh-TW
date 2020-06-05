---
title: 在 Q 中撰寫和模擬 qubit 層級程式#
description: 撰寫和模擬可在個別 qubit 層級運作之配量程式的逐步教學課程
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: 05d3292e1c6e3c8c1163c460f2aaa51c591aa1d5
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422235"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>教學課程：在 Q 中撰寫和模擬 qubit 層級程式\#

歡迎使用量子開發工具組教學課程，以撰寫和模擬可在個別 qubits 上運作的基本配量程式。 

雖然問 # 主要是針對大規模的量副程式建立為高階程式設計語言，但也可以輕鬆地用來探索較低層級的量副程式：直接定址特定的 qubits。
問 # 的彈性可讓使用者從任何這類抽象層處理量子系統，而在本教學課程中，我們會深入探討 qubits 本身。
具體而言，我們將探討「[量子傅立葉」轉換](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)的幕後，這是許多較大配量演算法不可或缺的副程式。

請注意，此低層級的配量資訊處理方式通常是以「[量子線路](xref:microsoft.quantum.concepts.circuits)」來描述，這代表將閘道的順序應用到特定的系統 qubits。

因此，我們依序套用的單一和多 qubit 作業可以在「電路圖」中輕鬆呈現。
在我們的案例中，我們將定義一個 Q # 作業來執行完整的三 qubit 配量傅立葉轉換，其具有下列標記法做為線路：

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Prerequisites

* 使用您慣用的語言和開發環境來[安裝](xref:microsoft.quantum.install)配量開發工具組。
* 如果您已安裝 QDK，請確定您已[更新](xref:microsoft.quantum.update)為最新版本


## <a name="in-this-tutorial-youll-learn-how-to"></a>在本教學課程中，您將了解如何：

> [!div class="checklist"]
> * 定義 Q 中的量子作業#
> * 直接從命令列呼叫 Q # 作業，或使用傳統主機程式
> * 模擬從 qubit 配置到測量輸出的量子作業
> * 觀察量子系統的模擬 wavefunction 在整個作業過程中的演變方式

使用 Microsoft 的量子開發工具組來執行量副程式，通常是由兩個部分組成：
1. 程式本身，使用 Q # 量副程式設計語言來執行，然後叫用以在量子電腦或量子模擬器上執行。 其中包括 
    - Q # 作業：在量子暫存器上作用的副程式，以及 
    - Q # 函式：在量子演算法內使用的傳統副程式。
2. 用來呼叫量副程式的進入點，並指定應該在其上執行的目的電腦。
    這可以直接從命令列進行，或透過以傳統程式設計語言（例如 Python 或 c #）撰寫的主機程式來完成。
    本教學課程包含您偏好的任何方法的指示。

## <a name="allocate-qubits-and-define-quantum-operations"></a>配置 qubits 並定義量子作業

本教學課程的第一個部分包含定義 Q # 作業，此作業會 `Perform3qubitQFT` 在三個 qubits 上執行量子傅立葉轉換。 

此外，我們將使用函式 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) 來觀察我們的三個 qubit 系統的模擬 wavefunction 如何在作業之間演變。

第一個步驟是建立您的 Q # 專案和檔案。
這項操作的步驟取決於您將用來呼叫程式的環境，您可以在個別的[安裝指南](xref:microsoft.quantum.install)中找到詳細資料。

我們會逐步引導您完成檔案的元件，但此程式碼也會以完整區塊的形式提供。

### <a name="namespaces-to-access-other-q-operations"></a>存取其他 Q # 作業的命名空間
在檔案中，我們會先定義 `NamespaceQFT` 將由編譯器存取的命名空間。
為了讓我們使用現有的 Q # 作業，我們會開啟相關的 `Microsoft.Quantum.<>` 命名空間。

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>定義具有引數的作業並傳回
接下來，我們會定義作業 `Perform3qubitQFT` ：

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

目前，此作業不會採用任何引數，也不會傳回任何---在此情況下，我們會寫出它傳回的 `Unit` 物件（在 c # 中類似于，而在 Python 中則是 `void` 空的元組） `Tuple[()]` 。
稍後，我們會將它修改為傳回測量結果的陣列，此時將會 `Unit` 取代此位置 `Result[]` 。 

### <a name="allocate-qubits-with-using"></a>使用配置 qubits`using`
在我們的 Q # 作業中，我們會先使用語句來配置三個 qubits 的暫存器 `using` ：

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

使用 `using` ，qubits 會自動設定在 $ \ket {0} $ 狀態中。 我們可以使用和來驗證這一點 [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) ，這會將字串和系統的目前狀態列印到主控台。

> [!NOTE]
> 和函式 `Message(<string>)` `DumpMachine()` （ [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) 分別來自和 [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) ）會直接列印到主控台。 就像實際的量子計算一樣，Q # 並不允許我們直接存取 qubit 狀態。
> 不過， `DumpMachine` 如果列印目的電腦的目前狀態，它可以在與完整狀態模擬器搭配使用時，提供用於進行偵錯工具和學習的寶貴見解。


### <a name="applying-single-qubit-and-controlled-gates"></a>套用單一 qubit 和受控制的閘道

接下來，我們會套用組成作業本身的閘道。
問 # 已包含許多基本配量閘道做為 [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) 命名空間中的作業，但這些不是例外狀況。 

在 Q # 作業中，將會以連續循序執行叫用 callables 的語句。
因此，第一個要套用的閘道是 [`H`](xref:microsoft.quantum.intrinsic.h) 第一個 qubit 的（Hadamard）：

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

若要將作業從暫存器（也就是陣列中的單一）套用至特定 qubit， `Qubit` `Qubit[]` 我們會使用標準索引標記法。
因此，將 [`H`](xref:microsoft.quantum.intrinsic.h) 套用至我們的註冊的第一個 qubit `qs` 會採用下列格式：

```qsharp
            H(qs[0]);
```

除了將 `H` （Hadamard）閘道套用至個別 qubits，QFT 電路主要是由控制的旋轉所組成 [`R1`](xref:microsoft.quantum.intrinsic.r1) 。
一般作業會將 `R1(θ, <qubit>)` qubit 的 $ \ket {0} $ 元件保持不變，同時將 $e ^ {i\theta} $ 的旋轉套用至 $ \ket {1} $ 元件。

#### <a name="controlled-operations"></a>控制的作業

問 # 讓在一或多個控制項 qubits 上執行作業的條件變得非常容易。
一般來說，我們只會在呼叫前面加 `Controlled` 上，而作業引數則會變更為：

 `Op(<normal args>)`$ \to $ `Controlled Op([<control qubits>], (<normal args>))` 。

請注意，控制項 qubits 必須當做陣列提供，即使它是單一 qubit 也是一樣。

在之後 `H` ，我們會看到下一個閘道是在 `R1` 第一個 qubit 上作用的閘道（並由第二個/第三個控制）：

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

我們稱之為

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

請注意，我們會使用命名空間中的函式 [`PI()`](xref:microsoft.quantum.math.pi) [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) ，以 pi 弧度來定義旋轉。
此外，我們 `Double` 會除以（例如）， `2.0` 因為除以整數 `2` 會擲回類型錯誤。 

> [!TIP]
> `R1(π/2)`和 `R1(π/4)` 相當於 `S` 和 `T` 作業（也是在中 `Microsoft.Quantum.Intrinsic` ）。


將相關的 `H` 作業和受控制的旋轉套用至第二個和第三個 qubits 之後：

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

我們只需要套用網 [`SWAP`](xref:microsoft.quantum.intrinsic.swap) 關來完成線路：

```qsharp
            SWAP(qs[2], qs[0]);
```

這是必要的，因為配量傅立葉轉換的本質會以反向順序輸出 qubits，因此，交換可讓副程式緊密整合成較大的演算法。

因此，我們已完成將配量傅立葉轉換的 qubit 層級作業寫入我們的 Q # 操作中：

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

不過，我們還無法一天呼叫它。
我們的 qubits 在配置時處於 $ \ket $ 的狀態 {0} ，而且在 Q # 中的運作方式很類似，我們應該以我們找到它們（或更棒）的相同方式來保留專案。

### <a name="deallocate-qubits"></a>解除配置 qubits

我們 [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) 再次呼叫以查看作業後的狀態，最後再套用至 qubit 暫存器， [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) 以在完成作業之前，將 qubits 重設為 $ \ket {0} $：

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

將所有已解除配置的 qubits 明確設定為 $ \ket {0} $ 是 Q # 的基本功能，因為它可讓其他作業在開始使用相同的 qubits （稀有資源）時，精確地得知其狀態。
此外，這可確保不會與系統中的任何其他 qubits 光子。
如果重設不是在配置區塊的結尾執行 `using` ，則會擲回執行階段錯誤。

您的完整 Q # 檔案現在看起來應該像這樣：

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


當 Q # 檔案和作業完成時，我們的配量程式已準備好進行呼叫和模擬。

## <a name="execute-the-program"></a>執行程式

在檔案中定義了我們的 Q # 作業之後 `.qs` ，我們現在需要呼叫該作業，並觀察所有傳回的傳統資料。
目前未傳回任何專案（請記得，上述定義的作業會傳回 `Unit` ），但當我們稍後修改 Q # 作業以傳回測量結果陣列（ `Result[]` ）時，我們會解決此問題。

雖然 Q # 程式在用來呼叫它的環境中很普遍，但執行此動作的方式當然會有所不同。 因此，只需遵循與您的安裝程式相對應的索引標籤中的指示：從 Q # 命令列應用程式運作，或在 Python 或 c # 中使用主機程式。

#### <a name="command-line"></a>[命令列](#tab/tabid-cmdline)

從命令列執行 Q # 程式，只需要稍微變更 Q # 檔案。

只要加 `@EntryPoint()` 到作業定義前面的一行：

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

若要執行程式，請開啟專案資料夾中的終端機，並輸入

```dotnetcli
dotnet run
```

執行時，您應該會 `Message` `DumpMachine` 在主控台中看到下列輸出。


#### <a name="python"></a>[Python](#tab/tabid-python)

建立 Python 主機檔案： `host.py` 。

主機檔案的結構如下所示： 
1. 首先，我們會匯入 `qsharp` 模組，以註冊 Q # 互通性的模組載入器。 
    這可讓問 # 命名空間（例如 `NamespaceQFT` 我們在 Q # 檔案中定義的）顯示為 Python 模組，我們可以從中匯入 Q # 作業。
2. 然後，匯入我們會直接叫用---的 Q # 作業，在此案例中為 `Perform3qubitQFT` 。
    我們只需要將進入點匯入 Q # 程式中（也就是_不_ `H` 是像是和的作業 `R1` ，由其他 Q # 作業呼叫，但傳統主機絕不會呼叫）。
3. 在模擬 Q # 作業或函數時，請使用表單在 `<Q#callable>.simulate(<args>)` `QuantumSimulator()` 目的電腦上執行。 

> [!NOTE]
> 如果我們想要在不同的電腦上呼叫作業，例如 `ResourceEstimator()` ，我們只會使用 `<Q#callable>.estimate_resources(<args>)` 。
> 一般來說，問 # 作業與執行所在的機器無關，但某些功能（例如） `DumpMachine` 可能會有不同的行為。

4. 執行模擬時，作業呼叫會傳回 Q # 檔案中定義的值。
    現在不會傳回任何內容，但稍後我們會看到指派和處理這些值的範例。
    透過我們手中的結果資料，並以完全傳統的方式進行，我們就可以執行任何想要的動作。

您的完整檔案應如下所 `host.py` 示：

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

執行 Python 檔案，並在您的主控台中列印，您應該會在 `Message` 下方看到和 `DumpMachine` 輸出。 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

遵循[安裝指南](xref:microsoft.quantum.install.cs)中的相同指示，建立 c # 主機檔案，並將它重新命名為 `host.cs` 。

C # 主機有四個部分：
1. 建構量子模擬器。
    在下列程式碼中，這是變數 `qsim` 。
2. 計算量子演算法所需的任何引數。
    此範例中沒有任何內容。
3. 執行量子演算法。 
    每個 Q# 作業都會產生一個具有相同名稱的 C# 類別。 
    此類別具有 `Run` 方法，會以**非同步方式**執行作業。
    執行是非同步的，因為實際硬體的執行將是非同步的。 
    因為 `Run` 方法是非同步，所以我們會呼叫 `Wait()` 方法，這會封鎖執行直到工作完成，並以同步方式傳回結果。 
4. 處理傳回的作業結果。
    目前，此作業不會傳回任何內容。


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
執行應用程式，您的輸出應該會符合以下的結果。
當您按下按鍵後，程式就會結束。
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

在完整狀態模擬器上呼叫時，會 `DumpMachine()` 提供量子狀態 wavefunction 的多個標記法。 $N $-qubit 系統的可能狀態可以用 $ 2 ^ n $ 計算基礎狀態表示，每一個都有對應的複雜係數（只是波幅和一個階段）。
計算基礎狀態會對應到長度 $n $---的所有可能二進位字串，也就是 qubit 狀態 $ \ket {0} $ 和 $ \ket $ 的所有可能組合 {1} ，其中每個二進位數位都會對應至個別的 qubit。

第一個資料列會以其重大順序提供批註，其中包含對應 qubits 的識別碼。
Qubit 是「 `2` 最重要」的意思，就是在基礎狀態向量 $ \ket{i} $ 的二進位標記法中，Qubit 的狀態會 `2` 對應到最左邊的數位。 例如，$ \ket {6} = \ket {110} $ 包含 qubits `2` ，以及 $ `1` \ket {1} $ 和 qubit `0` in $ \ket {0} $。


其餘的資料列會以笛卡和極座標格式來描述測量基礎狀態向量 $ \ket{i} $ 的機率幅度。
輸入狀態 $ \ket $ 的第一列詳細資料 {000} ：
* **`|0>:`** 這個資料列會對應到 `0` 計算基礎狀態（假設我們的初始狀態是 $ \ket {000} $，我們預期這是唯一的狀態，也就是機率振幅）。
* **`1.000000 +  0.000000 i`**：笛卡爾格式的機率幅度。
* **` == `**： `equal` 符號會分隔兩個對等的標記法。
* **`********************`**：大小的圖形表示，的數目與 `*` 測量此狀態向量的機率成正比。 
* **`[ 1.000000 ]`**：量值的數值
* **`    ---`**：振幅階段的圖形表示。
* **`[ 0.0000 rad ]`**：階段的數值（以弧度為單位）。

大小和階段都會以圖形標記法顯示。 量值的表示方式很簡單：它會顯示的橫條 `*` ，而機率越高，橫條就越大。 針對階段，請參閱[測試和偵錯工具：](xref:microsoft.quantum.guide.testingdebugging#dump-functions)根據角度範圍的可能符號表示傾印函式。


因此，列印的輸出會說明我們的程式設計閘道已將我們的狀態轉換為

$ $ \ket{\psi} \_ {初始值} = \ket {000} $ $

to 

$ $ \begin{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \left （\ket {000} + \ket {001} + \ket {010} + \ket {011} + \ket {100} + \ket {101} + \ket {110} + \ket {111} \right） \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}，\end{align} $ $

這正是 qubit 傅立葉轉換的行為。 

如果您想知道其他輸入狀態受到影響的方式，建議您在轉換之前，先套用 qubit 作業。

## <a name="adding-measurements"></a>新增測量

可惜的是，配量機制的基石告訴我們，實際的量子系統不能有這種 `DumpMachine` 功能。 相反地，我們會強制透過測量來解壓縮資訊，這通常不會使我們無法提供完整的量子狀態，而且也可以大幅改變系統本身。
配量測量有許多種，但我們會將焦點放在單一 qubits 上最基本的： projective 測量。
根據給定的測量單位（例如計算基礎 $ \{ \ket {0} 、\ket {1} \} $），qubit 狀態會投射到測量的任何基礎狀態---因此會摧毀兩者之間的任何重迭。

為了在 Q # 程式中執行測量，我們使用作業 `M` （來自 `Microsoft.Quantum.Intrinsic` ），它會傳回 `Result` 型別。

首先，我們會修改作業 `Perform3QubitQFT` 以傳回測量結果的陣列， `Result[]` 而不是 `Unit` 。

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>定義和初始化 `Result[]` 陣列

在配置 qubits 之前（也就是在 `using` 語句之前），我們會宣告並系結此長度為3的陣列（ `Result` 每個 qubit 一個）： 

```qsharp
        mutable resultArray = new Result[3];
```

`mutable`關鍵字前面 `resultArray` 允許稍後在程式碼中重新系結變數---例如，新增測量結果時。

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>在迴圈中執行測量 `for` ，並將結果新增至陣列

在區塊內的傅立葉轉換作業之後 `using` ，插入下列程式碼：

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)在陣列上呼叫的函式（例如，我們的 qubits 陣列 `qs` ）會傳回陣列索引上方的範圍。 在這裡，我們會在迴圈中使用它 `for` 來依序使用語句來測量每個 qubit `M(qs[i])` 。
然後，每個測量的 `Result` 類型（ `Zero` 或 `One` ）都會 `resultArray` 使用 update 和-重新指派語句加入至中的對應索引位置。

> [!NOTE]
> 此語句的語法對 Q # 而言是唯一的，但會對應到 `resultArray[i] <- M(qs[i])` 在其他語言（例如 F # 和 R）中所看到的類似變數重新指派。

關鍵字 `set` 一律用來重新指派使用系結的變數 `mutable` 。

#### <a name="return-resultarray"></a>退貨`resultArray`

所有三個 qubits 都經過測量並將結果新增至 `resultArray` 之後，我們就可以像之前一樣安全地重設和解除配置 qubits。
在 `using` 區塊的關閉之後，插入

```qsharp
        return resultArray;
```
最後傳回作業的輸出。 

### <a name="understanding-the-effects-of-measurement"></a>瞭解測量的效果

讓我們變更函式的位置 `DumpMachine` ，以輸出測量前後的狀態。
最後的作業程式碼看起來應該像這樣： 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

如果您是從命令列工作，傳回的陣列只會在執行結束時直接列印到主控台。
否則，請更新您的主機程式，以處理傳回的陣列。

#### <a name="command-line"></a>[命令列](#tab/tabid-cmdline)

若要更瞭解將在主控台中列印的傳回陣列，我們可以 `Message` 在語句之前的 Q # 檔案中新增另一個 `return` ：

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

執行專案，您的輸出看起來應該像下面這樣：

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

將您的 Python 程式更新為下列專案：

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

執行檔案，您的輸出看起來應該像下面這樣：

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

現在，我們的作業會傳回結果，請將方法呼叫取代 `Wait()` 為提取 `Result` 屬性。 這仍然可以達成稍早所討論的相同同步性，而且我們可以直接將此值系結至變數 `measurementResult` 。

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

執行專案，您的輸出看起來應該像下面這樣：

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

此輸出說明一些不同的事項：
1. 比較傳回的結果與預先測量 `DumpMachine` ，顯然不會說明 QFT _not_後重迭的基礎狀態。
    測量只會傳回單一的基礎狀態，其機率取決於系統 wavefunction 中該狀態的振幅。
2. 從後續測量開始 `DumpMachine` ，我們看到量值會_變更_狀態本身，並將其從初始重迭的基礎狀態投射到對應至測量值的單一基礎狀態。

如果我們多次重複此作業，我們會看到結果統計資料開始說明 QFT 後狀態的平均加權重迭，讓每個快照的隨機結果增加。
_不過_，除了效率不佳而且仍然完美，這只會重現基礎狀態的相對 amplitudes，而不是兩者之間的相對階段。
在此範例中，後者不是問題，但如果 QFT 的輸入比 $ \ket $ 更複雜，我們會看到相對階段出現 {000} 。

#### <a name="partial-measurements"></a>部分測量 
若要探索如何只測量暫存器的某些 qubits 可能會影響系統狀態，請嘗試在測量線之後將下列程式碼新增至 `for` 迴圈內：
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

請注意，若要存取函式， `IntAsString` 您必須新增 
```qsharp
    open Microsoft.Quantum.Convert;
```
加上命名空間語句的其餘部分 `open` 。

在產生的輸出中，您會在測量每個 qubit 時，看到逐漸投射到 subspaces 中。


## <a name="use-the-q-libraries"></a>使用 Q # 程式庫
如我們在簡介中所述，我們有許多問 # 的威力在於它可讓您抽象化處理個別 qubits 的擔心。
事實上，如果您想要開發完整規模、適用的量副程式，請擔心作業是在 `H` 特定旋轉之前或之後才會變慢。 

Q # 程式庫包含[QFT](xref:microsoft.quantum.canon.qft)作業，您可以直接採用並申請任何數目的 qubits。
若要試試看，請在您的 Q # 檔案中定義具有相同內容的新作業 `Perform3QubitQFT` ，但從第一個到的所有內容都是 `H` `SWAP` 由兩個簡單的程式程式碼所取代：
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
第一行只 [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) 會建立 qubits 的已配置陣列運算式， `qs` 這就是[QFT](xref:microsoft.quantum.canon.qft)作業做為引數所採用的方式。
這會對應到註冊中 qubits 的索引順序。

若要存取這些作業，請 `open` 在 Q # 檔案開頭新增其個別命名空間的語句：
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

現在，請調整您的主機程式，以呼叫新作業的名稱（例如 `PerformIntrinsicQFT` ），並為它提供 whirl。

若要查看使用 Q # 程式庫作業的實際優點，請將 qubits 的數目變更為以外的值 `3` ：
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
因此，您可以將適當的 QFT 套用到任何指定的 qubits 數目，而不必擔心新 `H` 作業和每個 qubit 的旋轉。

請注意，當您增加---qubits 數目時，配量模擬器會以指數方式執行較長的時間，因為我們會期待到真正的量子硬體。













