---
title: 建立量子亂數產生器
description: 建置一個 Q# 專案，透過建立量子亂數產生器來示範基本的量子概念，例如疊加。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: d1ad2c1153814e2fa19a38307b2c668c77eae4e3
ms.sourcegitcommit: b7e205aaa7fa1ca9f0daa163e46154945f4bc965
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2020
ms.locfileid: "77441065"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>快速入門：在 Q# 中實作量子亂數產生器
量子亂數產生器是以 Q # 撰寫量子演算法的一個簡單範例。 此演算法利用量子機制的本質來產生亂數。 

## <a name="prerequisites"></a>Prerequisites

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。
- [建立 Q# 專案](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>撰寫 Q# 作業

### <a name="q-operation-code"></a>Q# 作業程式碼

1. 以下列程式碼取代 Operation.qs 檔案的內容：

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

如[什麼是量子運算？](xref:microsoft.quantum.overview.what)文中所述，量子位元是一種可疊加的量子資訊單位。 測量時，量子位元只能是 0 或 1。 不過在執行期間，量子位元的狀態代表著測量讀數為 0 或 1 的機率。 這個概率性的狀態稱為疊加。 我們可以使用此機率來產生亂數。

在我們的 Q# 作業中，我們引進 Q# 原生的 `Qubit` 資料類型。 我們只能使用 `using` 陳述式來配置 `Qubit`。 當量子位元獲得配置時，一定會處於 `Zero` 狀態。 

使用 `H` 作業，我們可以將 `Qubit` 置於疊加狀態。 若要測量量子位元並讀取其值，請使用 `M` 內建作業。

藉由將 `Qubit` 置於疊加並加以測量，每次叫用程式碼時，結果就會是不同的值。 

解除配置 `Qubit` 時，必須將它明確設定回 `Zero` 狀態，否則模擬器將會報告執行階段錯誤。 叫用 `Reset` 是達成此動作的簡單做法。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>使用布洛赫球體將程式碼視覺化

在布洛赫球體中，北極點代表古典值 **0**，而南極點代表古典值 **1**。 任何疊加都可以用球體上的點表示 (以箭頭表示)。 箭頭末端愈接近極點時，量子位元在測量時塌縮為指派給該極點的古典值的機率愈高。 例如，下面紅色箭頭所表示的量子位元 狀態，在我們測量它時有較高的機率是 **0** 值。

<img src="~/media/qrng-Bloch.png" width="175">

我們可以用這個表示方式來將程式碼的作用視覺化呈現：

* 首先，我們讓量子位元的初始狀態為 **0**，並套用 `H` 來建立疊加，疊加的 **0** 和 **1** 機率相同。

<img src="~/media/qrng-H.png" width="450">

* 然後，我們測量量子位元並儲存輸出：

<img src="~/media/qrng-meas.png" width="450">

由於測量的結果完全隨機，我們便能得到一個隨機位元。 我們可以呼叫此作業多次來建立整數。 例如，如果我們呼叫此作業三次來取得三個隨機位元，則可以建立隨機的 3位元數字 (也就是介於 0 和 7 之間的亂數)。

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>使用主機程式建立完整的亂數產生器

既然我們已經有產生隨機位的 Q # 作業，我們可以用來建立完整的配量亂數產生器與主機程式。

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[使用 Visual Studio Code 或命令列的 Python](#tab/tabid-python)
 
 若要從 Python 執行新的 Q# 程式，請將下列程式碼儲存為 `host.py`：
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 然後，您可以從命令列執行 Python 主機程式：
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[使用 Visual Studio Code 或命令列的 C#](#tab/tabid-csharp)
 
 若要從 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 然後，您可以從命令列執行 C# 主機程式：
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[使用 Visual Studio 2019 的 C#](#tab/tabid-vs2019)

 若要從 Visual Studio 中的 C# 執行新的 Q# 程式，請修改 `Driver.cs` 以納入下列 C# 程式碼：

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 然後按 F5 鍵，程式會開始執行，並跳出一個新視窗顯示產生的亂數： 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
