---
title: 建立量子亂數產生器
description: 建置一個 Q# 專案，透過建立量子亂數產生器來示範基本的量子概念，例如疊加。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 18e8975e513a87c0a67a6dbb5586cc7dab5a93fb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274349"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>教學課程：在 Q\# 中實作量子亂數產生器

量子亂數產生器是以 Q # 撰寫量子演算法的一個簡單範例。 此演算法利用量子機制的本質來產生亂數。

## <a name="prerequisites"></a>必要條件

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。
- [從命令列使用 Q#](xref:microsoft.quantum.install.standalone)，或使用 [Python 主機程式](xref:microsoft.quantum.install.python) 或 [C# 主機程式](xref:microsoft.quantum.install.cs)，建立 Q# 專案。

## <a name="write-a-q-operation"></a>撰寫 Q# 作業

### <a name="q-operation-code"></a>Q# 作業程式碼

1. 使用下列程式碼取代 Program.qs 檔案的內容：

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

如[了解量子運算](xref:microsoft.quantum.overview.understanding)一文所述，量子位元是一種可疊加的量子資訊單位。 測量時，量子位元只能是 0 或 1。 不過在執行期間，量子位元的狀態代表著測量讀數為 0 或 1 的機率。 這個概率性的狀態稱為疊加。 我們可以使用此機率來產生亂數。

在我們的 Q# 作業中，我們引進 Q# 原生的 `Qubit` 資料類型。 我們只能使用 `using` 陳述式來配置 `Qubit`。 當量子位元獲得配置時，一定會處於 `Zero` 狀態。 

使用 `H` 作業，我們可以將 `Qubit` 置於疊加狀態。 若要測量量子位元並讀取其值，請使用 `M` 內建作業。

藉由將 `Qubit` 置於疊加並加以測量，每次叫用程式碼時，結果就會是不同的值。

解除配置 `Qubit` 時，必須將其明確設定回 `Zero` 狀態，否則模擬器將會報告執行階段錯誤。 叫用 `Reset` 是達成此動作的簡單做法。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>使用布洛赫球體將程式碼視覺化

在布洛赫球體中，北極點代表古典值 **0**，而南極點代表古典值 **1**。 任何疊加都可以用球體上的點表示 (以箭頭表示)。 箭頭末端愈接近極點時，量子位元在測量時塌縮為指派給該極點的古典值的機率愈高。 例如，下面紅色箭頭所表示的量子位元 狀態，在我們測量它時有較高的機率是 **0** 值。

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

我們可以用這個表示方式來將程式碼的作用視覺化呈現：

* 首先，我們讓量子位元的初始狀態為 **0**，並套用 `H` 來建立疊加，疊加的 **0** 和 **1** 機率相同。

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* 然後，我們測量量子位元並儲存輸出：

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

由於測量的結果完全隨機，我們便能得到一個隨機位元。 我們可以呼叫此作業多次來建立整數。 例如，如果我們呼叫此作業三次來取得三個隨機位元，則可以建立隨機的 3位元數字 (也就是介於 0 和 7 之間的亂數)。


## <a name="creating-a-complete-random-number-generator"></a>建立完整的亂數產生器

既然我們已經有產生隨機位元的 Q # 作業，我們可以用來建立完整的量子亂數產生器。 我們可以使用 Q # 命令列應用程式或使用主機程式。



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[具有 Visual Studio 或 Visual Studio Code 的 Q # 命令列應用程式](#tab/tabid-qsharp)

若要建立完整的 Q # 命令列應用程式，請將下列進入點新增至您的 Q # 程式： 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

視專案設定和命令列選項而定，可執行檔將會在模擬器或資源估計工具上執行標記為 `@EntryPoint()` 屬性的作業或函式。

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

在 Visual Studio 中，只要按 Ctrl + F5 執行指令碼即可。

在 VS Code 中，透過在終端機中輸入下列命令，以第一次建立 Program.qs：

```dotnetcli
dotnet build
```

在後續的執行中，不需要重新建立。 若要執行，請輸入下列命令並按 Enter 鍵：

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[使用 Visual Studio Code 或命令列的 Python](#tab/tabid-python)

若要從 Python 執行新的 Q# 程式，請將下列程式碼儲存為 `host.py`：

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

然後，您可以從命令列執行 Python 主機程式：

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[擁有 Visual Studio Code 或 Visual Studio 的 C#](#tab/tabid-csharp)

若要從 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

然後，您可以從命令列 (在 Visual Studio 中您必須按 F5) 執行 C# 主機程式：

```bash
$ dotnet run
The random number generated is 42
```

***