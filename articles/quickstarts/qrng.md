---
title: 建立量子亂數產生器
description: 建置一個 Q# 專案，透過建立量子亂數產生器來示範基本的量子概念，例如疊加。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443914"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>快速入門：在 Q# 中實作量子亂數產生器
量子亂數產生器是以 Q # 撰寫量子演算法的一個簡單範例。 此演算法利用量子機制的本質來產生亂數。 

## <a name="prerequisites"></a>必要條件

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。
- [建立 Q# 專案](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>撰寫 Q# 作業

### <a name="q-operation-code"></a>Q# 作業程式碼

1. 以下列程式碼取代 Operation.qs 檔案的內容：

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

如[什麼是量子運算？](xref:microsoft.quantum.overview.what)文中所述，量子位元是一種可疊加的量子資訊單位。 測量時，量子位元只能是 0 或 1。 不過在執行期間，量子位元的狀態代表著測量讀數為 0 或 1 的機率。 這個概率性的狀態稱為疊加。 我們可以使用此機率來產生亂數。

在我們的 Q# 作業中，我們引進 Q# 原生的 `Qubit` 資料類型。 我們只能使用 `using` 陳述式來配置 `Qubit`。 當量子位元獲得配置時，一定會處於 `Zero` 狀態。 

使用 `H` 作業，我們可以將 `Qubit` 置於疊加狀態。 若要測量量子位元並讀取其值，請使用 `M` 內建作業。

藉由將 `Qubit` 置於疊加並加以測量，每次叫用程式碼時，結果就會是不同的值。 

解除配置 `Qubit` 時，必須將它明確設定回 `Zero` 狀態，否則模擬器將會報告執行階段錯誤。 叫用 `Reset` 是達成此動作的簡單做法。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>使用布洛赫球體將程式碼視覺化

在布洛赫球體中，北極點代表古典值 **0**，而南極點代表古典值 **1**。 任何疊加都可以用球體上的點表示 (以箭頭表示)。 當箭頭末端愈接近極點時，量子位元在測量時塌縮為指派給該極點的古典值的機率愈高。 例如，下面紅色箭頭所表示的量子位元 狀態，在我們測量它時有較高的機率是 **0** 值。

<img src="./Bloch.svg" width="175">

我們可以用這個表示方式來將程式碼的作用視覺化呈現：

* 首先，我們讓量子位元的初始狀態為 **0**，並套用 `H` 來建立疊加，疊加的 **0** 和 **1** 機率相同。

<img src="./H.svg" width="450">

* 然後，我們測量量子位元並儲存輸出：

<img src="./Measurement2.svg" width="450">

由於測量的結果完全隨機，我們便能得到一個隨機位元。 我們可以呼叫此函式多次來建立整數。 例如，如果我們呼叫此函式三次來取得三個隨機位元，則可以建立隨機的 3位元數字 (也就是介於 0 和 7 之間的亂數)。
