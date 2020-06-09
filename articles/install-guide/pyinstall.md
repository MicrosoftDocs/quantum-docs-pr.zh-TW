---
title: '使用 Q # 和 Python 進行開發'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: f18d005012dc1c52aab456f1c7b194d182cab786
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578159"
---
# <a name="develop-with-q-and-python"></a>使用 Q # 和 Python 進行開發

安裝 QDK 以開發 Python 主機程式，以呼叫 Q # 作業。

1. 必要條件

    - [Python](https://www.python.org/downloads/) 3.6 或更新版本
    - [PIP](https://pip.pypa.io/en/stable/installing) Python 套件管理員
    - [.NET Core SDK 3。1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. 安裝 `qsharp` 套件，這是可在 Q # 和 Python 之間進行交互操作的 Python 套件。

    ```
    pip install qsharp
    ```

1. 安裝 IQ #，這是 Jupyter 和 Python 所使用的核心，可提供用來編譯和執行 Q # 作業的核心功能。

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. 雖然您可以在任何 IDE 中使用 Q # 搭配 Python，但強烈建議您為您的 Q # + Python 應用程式使用 Visual Studio Code （VS Code） IDE。 藉由使用 Visual Studio Code 和 QDK Visual Studio Code 延伸模組，您可以取得更豐富功能的存取權。

    - 安裝[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）
    - 安裝[適用于 VS Code 的 QDK 延伸](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)模組。

1. 建立 `Hello World` 應用程式來驗證安裝

    - 建立一個最小的 Q# 操作，方法是建立名為 `Operation.qs` 的檔案，再於其中新增下列程式碼：

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - 建立名為 `hello_world.py` 的 Python 程式，以呼叫 Q# `SayHello()` 操作：

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - 執行程式：

        ```
        python hello_world.py
        ```

    - 驗證輸出。 您的程式應該會輸出下列幾行：

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * 您也可以使用 Python Jupyter 筆記本來撰寫傳統的 Python 程式，並從資料格呼叫 Q # 作業。 Python 程式碼只是一般的 Python 程式。

## <a name="next-steps"></a>後續步驟

您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。
