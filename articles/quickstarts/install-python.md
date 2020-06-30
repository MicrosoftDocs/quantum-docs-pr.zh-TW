---
title: 使用 Q# 和 Python 進行開發
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274029"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="061b0-102">使用 Q# 和 Python 進行開發</span><span class="sxs-lookup"><span data-stu-id="061b0-102">Develop with Q# and Python</span></span>

<span data-ttu-id="061b0-103">安裝 QDK 來開發 Python 主機程式，以呼叫 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="061b0-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="061b0-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="061b0-104">Prerequisites</span></span>

    - <span data-ttu-id="061b0-105">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="061b0-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="061b0-106">[PIP](https://pip.pypa.io/en/stable/installing) Python 套件管理員</span><span class="sxs-lookup"><span data-stu-id="061b0-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="061b0-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="061b0-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="061b0-108">安裝 `qsharp` 封裝，此為允許 Q# 和 Python 之間互通的 Python 封裝。</span><span class="sxs-lookup"><span data-stu-id="061b0-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="061b0-109">安裝 IQ#，此為 Jupyter 與 Python 所使用的核心，可提供用於編譯與執行 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="061b0-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="061b0-110">如果在進行 `dotnet iqsharp install` 步驟期間發生錯誤，請開啟新的終端機視窗，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="061b0-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="061b0-111">如果仍無法解決問題，請嘗試找到已安裝的 `dotnet-iqsharp` 工具 (在 Windows 上則為 `dotnet-iqsharp.exe`)，並執行：</span><span class="sxs-lookup"><span data-stu-id="061b0-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="061b0-112">其中的 `/path/to/dotnet-iqsharp` 應以您檔案系統中 `dotnet-iqsharp` 工具的絕對路徑加以取代。</span><span class="sxs-lookup"><span data-stu-id="061b0-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="061b0-113">此工具通常位於您使用者設定檔資料夾中 `.dotnet/tools` 的下方。</span><span class="sxs-lookup"><span data-stu-id="061b0-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="061b0-114">雖然您可以在任何 IDE 中將 Q # 搭配 Python 使用，但強烈建議使用 Q # + Python 應用程式適用的 Visual Studio Code (VS Code) IDE。</span><span class="sxs-lookup"><span data-stu-id="061b0-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="061b0-115">透過使用 Visual Studio Code 與 QDK Visual Studio Code 擴充功能，您可以存取豐富的功能。</span><span class="sxs-lookup"><span data-stu-id="061b0-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="061b0-116">安裝 [VS Code](https://code.visualstudio.com/download) (Windows、Linux 和 Mac)</span><span class="sxs-lookup"><span data-stu-id="061b0-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="061b0-117">安裝 [VS Code 適用的 QDK 擴充功能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="061b0-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="061b0-118">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="061b0-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="061b0-119">建立一個最小的 Q# 操作，方法是建立名為 `Operation.qs` 的檔案，再於其中新增下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="061b0-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="061b0-120">建立名為 `hello_world.py` 的 Python 程式，以呼叫 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="061b0-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="061b0-121">執行程式：</span><span class="sxs-lookup"><span data-stu-id="061b0-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="061b0-122">驗證輸出。</span><span class="sxs-lookup"><span data-stu-id="061b0-122">Verify the output.</span></span> <span data-ttu-id="061b0-123">您的程式應該會輸出下列幾行：</span><span class="sxs-lookup"><span data-stu-id="061b0-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="061b0-124">您也可以使用 Python Jupyter Notebook 來撰寫傳統的 Python 程式，並從資料格呼叫 Q# 作業。</span><span class="sxs-lookup"><span data-stu-id="061b0-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="061b0-125">Python 程式碼只是一般的 Python 程式。</span><span class="sxs-lookup"><span data-stu-id="061b0-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="061b0-126">後續步驟</span><span class="sxs-lookup"><span data-stu-id="061b0-126">Next steps</span></span>

<span data-ttu-id="061b0-127">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="061b0-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
