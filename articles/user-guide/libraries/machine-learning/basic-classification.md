---
title: 使用配量 Machine Learning 程式庫的基本分類
description: '瞭解如何使用 Microsoft QDK 的量子 Machine Learning 程式庫，執行以 Q # 撰寫的量子順序分類器。'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274627"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>基本分類：使用 QDK 將資料分類

在本快速入門中，您將瞭解如何使用 QDK 的量子 Machine Learning 程式庫，執行以 Q # 撰寫的量子順序分類器。 

在本指南中，我們將使用在 Q # 中定義的分類器結構來使用半月球資料集。

## <a name="prerequisites"></a>必要條件

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。
- 建立適用于[Python 主機程式](xref:microsoft.quantum.install.python)或[c # 主機程式](xref:microsoft.quantum.install.cs)的 Q # 專案。

## <a name="host-program"></a>主機程式

您的主機套裝程式含三個部分：

- 載入資料集，並為您的模型選擇一組起始參數。
- 執行訓練來判斷模型的參數和偏差。
- 驗證模型以判斷其正確性

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[使用 Visual Studio Code 或命令列的 Python](#tab/tabid-python)

    若要執行，您是來自 Python 的 Q # 分類器，請將下列程式碼儲存為 `host.py` 。 請記住，您也需要在 `Training.qs` 本教學課程稍後說明的 Q # 檔案。

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    然後，您可以從命令列執行 Python 主機程式：

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[使用 Visual Studio Code 或命令列的 C#](#tab/tabid-csharp)

    若要執行，您是 c # 的 Q # 分類器，請將下列程式碼儲存為 `Host.cs` 。 請記住，您也需要在 `Training.qs` 本教學課程稍後說明的 Q # 檔案。

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    然後，您可以從命令列執行 C# 主機程式：

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[使用 Visual Studio 2019 的 C#](#tab/tabid-vs2019)

    若要從 Visual Studio 中的 c # 執行新的 Q # 程式，請修改 `Host.cs` 以包含下列 c # 程式碼。 請記住，您也需要在 `Training.qs` 本教學課程稍後說明的 Q # 檔案。

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    然後按 F5 鍵，程式會開始執行，並跳出一個新視窗顯示下列結果： 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q \# 分類器程式碼

現在讓我們來看看如何在 Q # 中定義主機程式所叫用的作業。
我們會將下列程式碼儲存在名為的檔案中 `Training.qs` 。

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

上述程式碼中所定義的最重要函式和作業如下：

- `ClassifierStructure() : ControlledRotation[]`：在此函式中，我們會藉由新增我們所考慮之受控制閘道的層級，來設定線路模型的結構。 此步驟類似于連續深度學習模型中的神經層級宣告。
- `TrainHalfMoonModel() : (Double[], Double)`：此作業是程式碼的核心部分，會定義定型。 在這裡，我們會從程式庫中包含的資料集載入範例，我們會設定定型的超參數和初始參數，並藉由呼叫程式庫中包含的作業來開始定型 `TrainSequentialClassifier` 。 它會輸出參數和判斷分類器的偏差。
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`：此作業會定義用來評估模型的驗證程式。 在這裡，我們會載入用於驗證的範例、每個樣本的度量數目和容錯。 它會輸出所選樣本批次的 misclassifications 數目以進行驗證。

## <a name="next-steps"></a>後續步驟

首先，您可以使用程式碼，並嘗試變更某些參數，以查看它對定型的影響。 接著，在下一個教學課程中，[設計您自己的分類器](xref:microsoft.quantum.libraries.machine-learning.design)，您將學習如何定義分類器的結構。
