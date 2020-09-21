---
title: 撰寫和模擬中的量子位層級程式 Q#
description: 撰寫和模擬在個別量子位層級運作之量副程式的逐步教學課程
author: gillenhaalb
ms.author: a-gibec
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0dbeee8e092c830576ba8f79733035cdeeac11de
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834953"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>教學課程：在 Q 中撰寫和模擬量子位層級程式\#

歡迎使用量子開發工具組教學課程，以撰寫和模擬在個別量子位上運作的基本量副程式。 

雖然 Q# 主要是建立為大規模量副程式的高階程式設計語言，但它可以輕鬆地用來探索較低層級的量副程式：直接定址特定的量子位。
的彈性 Q# 可讓使用者從任何這類抽象層處理量子系統，在本教學課程中，我們會深入探討量子位本身。
具體而言，我們會看看 [量子傅立葉轉換](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)的本質，這是許多較大型量子演算法不可或缺的副程式。

請注意，此量子資訊處理的低層級視圖通常是以「[量子線路](xref:microsoft.quantum.concepts.circuits)」來描述，這代表系統的特定量子位之閘道的順序應用。

因此，我們順序套用的單一和多量子位作業，可以立即以「電路圖」表示。
在我們的案例中，我們將定義一項作業 Q# 來執行完整的三量子位量子傅立葉轉換，其以下列標記法作為電路：

<br/>
<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Prerequisites

* 使用您慣用的語言和開發環境，[安裝](xref:microsoft.quantum.install)量子開發工具組。
* 如果您已安裝 QDK，請確定您已[更新](xref:microsoft.quantum.update)為最新版本


## <a name="in-this-tutorial-youll-learn-how-to"></a>在本教學課程中，您將了解如何：

> [!div class="checklist"]
> * 定義中的量子作業 Q#
> * Q#從命令提示字元或使用傳統主機程式直接呼叫作業
> * 模擬從量子位配置到測量輸出的量子運算
> * 觀察量子系統的模擬 wavefunction 如何在整個作業中演進

使用 Microsoft 的量子開發工具組執行量副程式通常是由兩個部分所組成：
1. 程式本身，它會使用 Q# 量副程式設計語言來執行，然後叫用以在量子電腦或量子模擬器上執行。 這些包含 
    - Q# 作業：在量子暫存器上作用的副程式，以及 
    - Q# 函數：量子演算法內使用的傳統副程式。
2. 用來呼叫量副程式的進入點，並指定應該在其上執行的目的電腦。
    這可以直接從命令提示字元執行，或透過以傳統程式設計語言（例如 Python 或 c #）撰寫的主機程式來完成。
    本教學課程包含您偏好之任何方法的指示。

## <a name="allocate-qubits-and-define-quantum-operations"></a>配置量子位並定義量子作業

本教學課程的第一個部分包含定義作業，此作業會 Q# `Perform3qubitQFT` 在三個量子位上執行量子傅立葉轉換。 

此外，我們將使用函式 [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) 來觀察三個量子位系統的模擬 wavefunction 如何在整個作業中演進。

第一個步驟是建立您的 Q# 專案和檔案。
這項操作的步驟取決於您將用來呼叫程式的環境，而且您可以在個別的 [安裝指南](xref:microsoft.quantum.install)中找到詳細資料。

我們會逐步引導您完成檔案的元件，但是程式碼也是以完整區塊的形式提供。

### <a name="namespaces-to-access-other-no-locq-operations"></a>存取其他作業的命名空間 Q#
在檔案中，我們會先定義 `NamespaceQFT` 編譯器將存取的命名空間。
為了讓我們的作業使用現有的 Q# 作業，我們開啟了相關的 `Microsoft.Quantum.<>` 命名空間。

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>使用引數和傳回來定義作業
接下來，我們會定義作業 `Perform3qubitQFT` ：

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

目前，此作業不會採用任何引數，也不會傳回任何---在此案例中，我們會撰寫它 `Unit` 會傳回類似于 `void` c # 中的物件，或在 Python 中為空的元組 `Tuple[()]` 。
稍後，我們會將它修改為傳回測量結果的陣列，此時將會 `Unit` 由取代 `Result[]` 。 

### <a name="allocate-qubits-with-using"></a>配置量子位 `using`
在我們 Q# 的作業中，我們會先使用語句配置三個量子位的註冊 `using` ：

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

使用時 `using` ，量子位會自動以 $ \ket {0} $ 狀態進行配置。 我們可以使用和來確認這一點 [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) ，這會將字串和系統的目前狀態列印到主控台。

> [!NOTE]
> 和函式 `Message(<string>)` `DumpMachine()` (自 [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) 和 [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) ，分別) 會直接列印到主控台。 就像實際的量子運算一樣， Q# 無法讓我們直接存取量子位狀態。
> 不過，由於會 `DumpMachine` 列印目的電腦的目前狀態，它可以提供在搭配完整狀態模擬器使用時進行偵錯工具和學習的寶貴見解。


### <a name="applying-single-qubit-and-controlled-gates"></a>套用單一量子位和控制的閘道

接下來，我們會套用組成作業本身的閘道。
Q# 已包含許多基本量子閘道作為命名空間中的作業 [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) ，而且這些不是例外狀況。 

在作業中 Q# ，叫用 callables 的語句當然會依序執行。
因此，第一個要套用的閘道是 [`H`](xref:microsoft.quantum.intrinsic.h) 第一個量子位的 (Hadamard) ：

<br/>
<img src="../media/qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

若要 (從登錄將作業套用至特定量子位，也就是 `Qubit` 從陣列中的單一 `Qubit[]`) 我們使用標準索引標記法。
因此，將 [`H`](xref:microsoft.quantum.intrinsic.h) 套用至我們的註冊的第一個量子位 `qs` 會採用下列格式：

```qsharp
            H(qs[0]);
```

除了將 `H` (Hadamard) 閘道套用至個別量子位，QFT 電路主要是由受控制的旋轉所組成 [`R1`](xref:microsoft.quantum.intrinsic.r1) 。
一般作業會將 `R1(θ, <qubit>)` 量子位的 $ \ket {0} $ 元件保持不變，同時將 $e ^ {i\theta} $ 的旋轉套用至 $ \ket {1} $ 元件。

#### <a name="controlled-operations"></a>控制的作業

Q# 讓您在一或多個控制項量子位上執行作業時非常容易。
一般而言，我們只是在呼叫前面加 `Controlled` 上，而作業引數的變更如下：

 `Op(<normal args>)` $ \to $ `Controlled Op([<control qubits>], (<normal args>))` 。

請注意，您必須以陣列形式提供控制項量子位，即使它是單一量子位也一樣。

之後 `H` ，我們會看到下一個閘道是 `R1` 在第一個量子位 (的閘道，並由第二個/第三個) 控制：

<br/>
<img src="../media/qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

我們稱之為

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

請注意，我們會使用 [`PI()`](xref:microsoft.quantum.math.pi) 來自命名空間的函式 [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) ，以 pi 弧度來定義旋轉。
此外，我們 `Double` 會除以 (例如) ， `2.0` 因為除以整數 `2` 會擲回類型錯誤。 

> [!TIP]
> `R1(π/2)` 和 `R1(π/4)` 也相當於 `S` 和 `T` 作業 (也在 `Microsoft.Quantum.Intrinsic`) 中。


將相關的 `H` 作業和控制的旋轉套用至第二個和第三個量子位之後：

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

我們只需要套用一個網 [`SWAP`](xref:microsoft.quantum.intrinsic.swap) 關來完成線路：

```qsharp
            SWAP(qs[2], qs[0]);
```

這是必要的，因為量子傅立葉轉換的本質會以反向順序輸出量子位，因此交換可讓副程式緊密整合到較大的演算法。

因此，我們已完成將量子傅立葉轉換的量子位層級作業寫入我們的作業中 Q# ：

<img src="../media/qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

不過，我們還無法在一天之前呼叫它。
當我們配置量子位時，我們的州/省是 $ \ket {0} $，很像在現實生活中， Q# 我們應該以與我們一樣的方式，將專案保留 (或更好！ ) 。

### <a name="deallocate-qubits"></a>解除配置量子位

我們 [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) 再次呼叫以查看作業後狀態，最後會套用至量子位暫存器， [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) 以在完成作業之前將量子位重設為 $ \ket {0} $：

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

要求所有已解除配置的量子位都明確設定為 $ \ket {0} $ 是的基本功能 Q# ，因為它可讓其他作業在開始使用這些相同的量子位 (稀有資源) 時，精確地知道其狀態。
此外，這可確保它們不會與系統中的任何其他量子位纏結。
如果未在配置區塊的結尾執行重設，則會擲回 `using` 執行階段錯誤。

您的完整檔案 Q# 現在看起來應該像這樣：

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


完成檔案 Q# 和作業之後，就可以呼叫和模擬我們的量副程式。

## <a name="run-the-program"></a>執行程式

在檔案中定義我們的作業之後 Q# `.qs` ，我們現在需要呼叫該作業，並觀察任何傳回的傳統資料。
目前，沒有任何傳回的 (回想，上述定義的作業會傳回 `Unit`) ，但是當我們稍後修改作業 Q# 以傳回測量結果陣列 (`Result[]`) 時，我們將會解決此情況。

雖然 Q# 程式在用來呼叫它的環境中是普遍的，但這麼做的方式當然會有所不同。 因此，只要依照您的設定所對應的索引標籤中的指示操作：從 Q# 應用程式或使用 Python 或 c # 中的主機程式來運作。

#### <a name="command-prompt"></a>[命令提示字元](#tab/tabid-cmdline)

Q#從命令提示字元執行程式，只需要對檔案進行少許變更 Q# 。

只要新增 `@EntryPoint()` 至作業定義前面的一行即可：

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

若要執行程式，請在專案的資料夾中開啟終端機，並輸入

```dotnetcli
dotnet run
```

完成時，您應該會 `Message` `DumpMachine` 在主控台中看到下列輸出和輸出。


#### <a name="python"></a>[Python](#tab/tabid-python)

建立 Python 主機檔案： `host.py` 。

主機檔案的結構如下： 
1. 首先，我們會匯入 `qsharp` 模組，該模組會註冊模組載入器以獲得 Q# 互通性。 
    這可讓 Q# 命名空間 (例如， `NamespaceQFT` 我們在檔案中定義的 Q#) 會顯示為 Python 模組，我們可以從中匯入 Q# 作業。
2. 然後，匯入 Q# 我們將在此案例中直接叫用---的作業 `Perform3qubitQFT` 。
    我們只需要將進入點匯入程式中， Q# (也_not_就是不 `H` 是與等作業 `R1` ，由其他 Q# 作業呼叫，但傳統主機) 絕不會呼叫。
3. 在模擬 Q# 作業或函式時，請使用表單在 `<Q#callable>.simulate(<args>)` `QuantumSimulator()` 目的電腦上執行。 

> [!NOTE]
> 例如，如果我們想要在不同的電腦上呼叫此作業， `ResourceEstimator()` 我們只需要使用 `<Q#callable>.estimate_resources(<args>)` 。
> 一般情況下， Q# 作業與執行所在的電腦無關，但某些功能（例如） `DumpMachine` 可能會有不同的行為。

4. 執行模擬時，操作呼叫會傳回檔案中定義的值 Q# 。
    現在沒有傳回任何內容，但稍後我們會看到指派和處理這些值的範例。
    有了結果的資料，我們就可以用它來做任何想要的結果。

您的完整檔案應如下所 `host.py` 示：

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

執行 Python 檔案，並列印在主控台中，您應該會看到 `Message` `DumpMachine` 下列輸出。 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

遵循《 [安裝指南》](xref:microsoft.quantum.install.cs)中的相同指示，建立 c # 主機檔案，然後將它重新命名為 `host.cs` 。

C # 主機有四個部分：
1. 建構量子模擬器。
    在下列程式碼中，這是變數 `qsim` 。
2. 計算量子演算法所需的任何引數。
    此範例中沒有任何內容。
3. 執行量子演算法。 
    每個作業 Q# 都會產生具有相同名稱的 c # 類別。 
    此類別的 `Run` 方法會以 **非同步方式**執行作業。
    執行是非同步，因為在實際的硬體上執行它將會是非同步。 
    因為此 `Run` 方法是非同步，所以我們會呼叫 `Wait()` 方法; 這會封鎖執行，直到工作完成並以同步方式傳回結果為止。 
4. 處理傳回的作業結果。
    目前，作業不會傳回任何內容。


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
執行應用程式，您的輸出應該會符合下面的結果。
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

在完整狀態模擬器上呼叫時，會 `DumpMachine()` 提供這些量子狀態 wavefunction 的多重標記法。 $N $-量子位系統的可能狀態可以用 $ 2 ^ n $ 計算基礎狀態表示，每一個都有相對應的複數 (只是一個振幅和一個階段) 。
計算基礎狀態會對應至長度 $n $---的所有可能二進位字串，也就是量子位狀態 $ \ket {0} $ 和 $ \ket $ 的所有可能組合 {1} ，其中每個二進位數都對應到個別量子位。

第一個資料列會以其重大順序提供批註，內含對應量子位的識別碼。
量子位是「 `2` 最重要的」，只是表示在基礎狀態向量 $ \ket{i} $ 的二進位標記法中，量子位的狀態 `2` 對應到最左邊的數位。 例如，$ \ket {6} = \ket {110} $ 的組成量子位 `2` ，以及 $ `1` \ket {1} $ 和量子位 `0` in $ \ket {0} $。


其餘的資料列描述測量以笛卡兒和極座標形式測量基礎狀態向量 $ \ket{i} $ 的機率幅度。
針對輸入狀態 $ \ket $ 的第一列詳細資料 {000} ：
* **`|0>:`** 此資料列對應于 `0` 計算基礎狀態 (假設我們的初始狀態後置配置為 $ \ket {000} $，則會預期這是具有機率幅度的唯一狀態) 。
* **`1.000000 +  0.000000 i`**：笛卡兒格式的機率幅度。
* **` == `**： `equal` 符號會分隔兩個對等的表示。
* **`********************`**：量值的圖形表示，的數目 `*` 會與測量這個狀態向量的機率成正比。 
* **`[ 1.000000 ]`**：量值的數值
* **`    ---`**：振幅階段的圖形表示。
* **`[ 0.0000 rad ]`**：階段的數值 (弧度) 。

大小和階段都會以圖形表示顯示。 量值的表示方式很簡單：它會顯示一個橫條 `*` ，而機率愈高，則會顯示較大的橫條。 針對階段，請參閱 [測試和偵測：](xref:microsoft.quantum.guide.testingdebugging#dump-functions) 根據角度範圍的可能符號表示傾印函數。


因此，列印的輸出會說明我們的程式設計閘道將我們的狀態轉換為

$ $ \ket{\psi} \_ {初始} = \ket {000} $ $

至 

$ $ \begin{align} \ket{\psi} \_ {final} &= \frac {1} {\sqrt {8} } \left ( \ket {000} + \ket {001} + \ket + \ket {010} {011} + \ket {100} + \ket {101} + \ket + \ket {110} {111} \right) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}，\end{align} $ $

這是量子位傅立葉轉換的精確行為。 

如果您對其他輸入狀態的影響有好奇，建議您在轉換之前，先套用量子位作業。

## <a name="adding-measurements"></a>新增度量

可惜的是，量子機制的基石告訴我們，真正的量子系統不能有這類 `DumpMachine` 功能。 相反地，我們會強制透過度量來解壓縮資訊，而這通常不僅無法提供我們完整的量子狀態，還能大幅改變系統本身。
量子測量有許多種，但我們會將焦點放在單一量子位上最基本的： projective 測量。
以給定的度量進行測量時 (例如，計算基礎 $ \{ \ket {0} 、\ket {1} \} $) 、量子位狀態會投射到任何測量的基礎狀態---因此會終結兩者之間的任何迭加。

為了在程式內執行度量 Q# ，我們會使用 `M` 從) 傳回類型的作業 (`Microsoft.Quantum.Intrinsic` `Result` 。

首先，我們會修改作業 `Perform3QubitQFT` 來傳回測量結果的陣列， `Result[]` 而不是 `Unit` 。

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>定義和初始化 `Result[]` 陣列

在甚至是配置量子位之前 (也就是在 `using` 語句) 之前，我們會宣告並系結此長度3陣列 (`Result` 每個量子位) 各一個： 

```qsharp
        mutable resultArray = new Result[3];
```

`mutable`關鍵字接下來 `resultArray` 允許稍後在程式碼中重新綁定變數---例如，在新增測量結果時。

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>在迴圈中執行測量 `for` ，並將結果新增至陣列

在區塊內的傅立葉轉換作業之後 `using` ，插入下列程式碼：

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)在陣列上呼叫的函式 (例如我們量子位的陣列， `qs`) 傳回陣列索引的範圍。 在這裡，我們會在迴圈中使用它， `for` 以依序使用語句來測量每個量子位 `M(qs[i])` 。
每個測量的 `Result` 類型 (`Zero` 或 `One`) 接著會 `resultArray` 使用 update 和重新指派語句新增至中的對應索引位置。

> [!NOTE]
> 這個語句的語法對而言是唯一的 Q# ，但是會對應到 `resultArray[i] <- M(qs[i])` 其他語言（例如 F # 和 R）中所看到的類似變數重新指派。

關鍵字 `set` 一律用來重新指派使用系結的變數 `mutable` 。

#### <a name="return-resultarray"></a>返回 `resultArray`

所有三個量子位都經過測量，並將結果加入至 `resultArray` 之後，我們就可以安全地重設和解除配置量子位。
在 `using` 區塊關閉之後，插入

```qsharp
        return resultArray;
```
最後會傳回作業的輸出。 

### <a name="understanding-the-effects-of-measurement"></a>瞭解測量的影響

讓我們變更函式的位置， `DumpMachine` 以輸出度量前後的狀態。
最終的作業程式碼看起來應該像這樣： 

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

如果您是從命令提示字元工作，傳回的陣列只會在執行結束時直接顯示在主控台中。
否則，請更新您的主機程式以處理傳回的陣列。

#### <a name="command-prompt"></a>[命令提示字元](#tab/tabid-cmdline)

若要更瞭解將在主控台中列印的傳回陣列，我們可以 `Message` 在語句之前的檔案中加入另一個 Q# `return` ：

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

執行專案，您的輸出看起來應該會如下所示：

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

將您的 Python 程式更新為下列內容：

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

執行檔案，您的輸出看起來應該會如下所示：

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

現在，我們的作業會傳回結果，請 `Wait()` 以提取屬性取代方法呼叫 `Result` 。 這仍會完成先前討論過的相同同步性，我們可以直接將此值系結至變數 `measurementResult` 。

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

執行專案，您的輸出看起來應該會如下所示：

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

此輸出說明一些不同的專案：
1. 將傳回的結果與預先度量比較 `DumpMachine` ，顯然不會說明_not_ QFT 後迭加的基礎狀態。
    度量只會傳回單一基礎狀態，並在系統 wavefunction 中以該狀態的波幅決定機率。
2. 從之後的測量結果 `DumpMachine` ，我們發現測量 _改變_ 了狀態本身，將其從初始迭加的基礎狀態投射到對應至測量值的單一基礎狀態。

如果我們要重複執行這項作業多次，我們會看到結果統計資料開始說明 QFT 後狀態的平均加權迭加，這會導致每個快照的隨機結果。
_但是_，除了效率不佳且仍然完美之外，這只會重現基礎狀態的相對 amplitudes，而不是兩者之間的相對階段。
後者在此範例中並不是問題，但如果提供比 $ \ket $ 更複雜的 QFT 輸入，則會看到相對階段。 {000}

#### <a name="partial-measurements"></a>部分度量 
若要探索如何只測量註冊的部分量子位可能會影響系統的狀態，請嘗試在 `for` 測量線之後，于迴圈內新增下列程式碼：
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

請注意，若要存取函式， `IntAsString` 您將必須新增 
```qsharp
    open Microsoft.Quantum.Convert;
```
以及命名空間語句的其餘部分 `open` 。

在產生的輸出中，您會在測量每個量子位時看到逐步投射至 subspaces。


## <a name="use-the-no-locq-libraries"></a>使用連結 Q# 庫
如同我們在簡介中所述，大部分的 Q# 功能都能讓您抽象化處理個別的量子位。
事實上，如果您想要開發全方位、適用的量副程式，請擔心某項作業 `H` 在特定輪替之前或之後是否會變慢。 

連結 Q# 庫包含 [QFT](xref:microsoft.quantum.canon.qft) 作業，您可以直接採用並套用至任意數目的量子位。
若要試試看，請在您的檔案中定義 Q# 具有相同內容的新作業 `Perform3QubitQFT` ，但是從第一個的所有專案，都是 `H` `SWAP` 由兩個簡單的程式碼所取代：
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
第一行只 [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) 會建立已配置量子位陣列的運算式， `qs` 這是 [QFT](xref:microsoft.quantum.canon.qft) 作業做為引數所採用的運算式。
這對應于註冊中量子位的索引順序。

若要存取這些作業，請 `open` 在檔案的開頭新增其各自命名空間的語句 Q# ：
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

現在，調整您的主機程式以呼叫新作業的名稱 (例如 `PerformIntrinsicQFT`) ，並為其提供 whirl。

若要瞭解使用程式庫作業的真正優點 Q# ，請將量子位數目變更為以下以外的值 `3` ：
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
因此，您可以針對任何指定的量子位數目套用適當的 QFT，而不需要擔心 `H` 每個量子位的新作業和旋轉。

請注意，當您增加量子位數目時，量子模擬器會以指數方式執行一次以上的時間，---精確地查看真正的量子硬體！













