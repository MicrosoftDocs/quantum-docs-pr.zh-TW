---
title: '使用 Q # 和 Python 進行開發'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 35499daae0cd0ae329e39b43b0d8dd5a00183871
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660738"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="92090-102">使用 Q # 和 Python 進行開發</span><span class="sxs-lookup"><span data-stu-id="92090-102">Develop with Q# and Python</span></span>

<span data-ttu-id="92090-103">安裝 QDK 以開發 Python 主機程式，以呼叫 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="92090-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="92090-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="92090-104">Pre-requisites</span></span>

    - <span data-ttu-id="92090-105">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="92090-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="92090-106">[PIP](https://pip.pypa.io/en/stable/installing) Python 套件管理員</span><span class="sxs-lookup"><span data-stu-id="92090-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="92090-107">.NET Core SDK 3。1</span><span class="sxs-lookup"><span data-stu-id="92090-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="92090-108">安裝 `qsharp` 套件，這是可在 Q # 和 Python 之間進行交互操作的 Python 套件。</span><span class="sxs-lookup"><span data-stu-id="92090-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="92090-109">安裝 IQ #，這是 Jupyter 和 Python 所使用的核心，可提供用來編譯和執行 Q # 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="92090-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="92090-110">雖然您可以在任何 IDE 中使用 Q # 搭配 Python，但強烈建議您為您的 Q # + Python 應用程式使用 Visual Studio Code （VS Code） IDE。</span><span class="sxs-lookup"><span data-stu-id="92090-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="92090-111">藉由使用 Visual Studio Code 和 QDK Visual Studio Code 延伸模組，您可以取得更豐富功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="92090-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="92090-112">安裝[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="92090-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="92090-113">安裝[適用于 VS Code 的 QDK 延伸](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)模組。</span><span class="sxs-lookup"><span data-stu-id="92090-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="92090-114">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="92090-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="92090-115">建立一個最小的 Q# 操作，方法是建立名為 `Operation.qs` 的檔案，再於其中新增下列程式碼：</span><span class="sxs-lookup"><span data-stu-id="92090-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="92090-116">建立名為 `hello_world.py` 的 Python 程式，以呼叫 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="92090-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="92090-117">執行程式：</span><span class="sxs-lookup"><span data-stu-id="92090-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="92090-118">驗證輸出。</span><span class="sxs-lookup"><span data-stu-id="92090-118">Verify the output.</span></span> <span data-ttu-id="92090-119">您的程式應該會輸出下列幾行：</span><span class="sxs-lookup"><span data-stu-id="92090-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="92090-120">您也可以使用 Python Jupyter 筆記本來撰寫傳統的 Python 程式，並從資料格呼叫 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="92090-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="92090-121">Python 程式碼只是一般的 Python 程式。</span><span class="sxs-lookup"><span data-stu-id="92090-121">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="92090-122">後續步驟</span><span class="sxs-lookup"><span data-stu-id="92090-122">Next steps</span></span>

<span data-ttu-id="92090-123">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="92090-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
