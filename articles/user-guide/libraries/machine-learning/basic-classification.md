---
title: 量子 Machine Learning 程式庫的基本分類
description: 瞭解如何 Q# 使用 MICROSOFT QDK 的量子 Machine Learning 程式庫，執行以所撰寫的量子順序分類器。
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5dc4614b9992e2c6b9f8ff4b839c0929ec8cab7c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833711"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>基本分類：使用 QDK 分類資料

在本快速入門中，您將瞭解如何使用 QDK 的量子 Machine Learning 程式庫，執行以所撰寫的量子順序分類器 Q# 。 

在本指南中，我們將使用中定義的分類器結構來使用半衛星資料集 Q# 。

## <a name="prerequisites"></a>Prerequisites

- Microsoft [Quantum Development Kit](xref:microsoft.quantum.install)。
- Q#為[Python 主機程式](xref:microsoft.quantum.install.python)或[c # 主機程式](xref:microsoft.quantum.install.cs)建立專案。

## <a name="host-program"></a>主機程式

您的主機程式是由三個部分所組成：

- 載入資料集，然後為您的模型選擇一組起始參數。
- 執行定型以判斷模型的參數和偏差。
- 驗證模型以判斷其精確度

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[使用 Visual Studio Code 或命令列的 Python](#tab/tabid-python)

    若要執行您是 Q# Python 的分類器，請將下列程式碼儲存為 `host.py` 。 請記住，您也需要 Q# `Training.qs` 本教學課程稍後說明的檔案。

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    然後，您可以從命令列執行 Python 主機程式：

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[使用 Visual Studio Code 或命令列的 C#](#tab/tabid-csharp)

    若要執行您是 Q# c # 的分類器，請將下列程式碼儲存為 `Host.cs` 。 請記住，您也需要 Q# `Training.qs` 本教學課程稍後說明的檔案。

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    然後，您可以從命令列執行 C# 主機程式：

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[使用 Visual Studio 2019 的 C#](#tab/tabid-vs2019)

    若要 Q# 在 Visual Studio 中從 c # 執行新程式，請修改 `Host.cs` 以包含下列 c # 程式碼。 請記住，您也需要 Q# `Training.qs` 本教學課程稍後說明的檔案。

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    按下 F5 鍵，程式就會開始執行。 新視窗會顯示下列結果： 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q \# 分類程式代碼

現在讓我們看看如何定義主機程式叫用的作業 Q# 。
我們會將下列程式碼儲存在名為的檔案中 `Training.qs` 。

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

上述程式碼中定義的最重要函數和作業如下：

- `ClassifierStructure() : ControlledRotation[]` ：在此函式中，我們會藉由新增我們所考慮之受控制閘道的層級，來設定電路模型的結構。 此步驟類似于連續深度學習模型中的神經層級聲明。
- `TrainHalfMoonModel() : (Double[], Double)` ：這項作業是程式碼的核心部分，並定義定型。 在這裡，我們會從程式庫中所包含的資料集載入範例、為定型設定超參數和初始參數，然後藉由呼叫程式庫中所包含的作業來開始定型 `TrainSequentialClassifier` 。 它會輸出決定分類器的參數和偏差。
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` ：此作業會定義用來評估模型的驗證程式。 在這裡，我們會載入驗證範例、每個樣本的度量數目和容錯。 它會輸出所選樣本批次的情形數目以進行驗證。

## <a name="next-steps"></a>後續步驟

首先，您可以使用程式碼，並嘗試變更某些參數，以查看它對定型的影響。 然後，在下一個教學課程中， [設計您自己的分類器](xref:microsoft.quantum.libraries.machine-learning.design)，您將學習如何定義分類器的結構。
