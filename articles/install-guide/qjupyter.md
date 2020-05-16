---
title: '使用 Q # Jupyter 筆記本進行開發'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 38db14ccc5f2406043ff4baee3f562385cdf47a8
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426385"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="54422-102">使用 Q # Jupyter 筆記本進行開發</span><span class="sxs-lookup"><span data-stu-id="54422-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="54422-103">安裝 QDK 以在 Q # Jupyter 筆記本上開發 Q # 作業。</span><span class="sxs-lookup"><span data-stu-id="54422-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="54422-104">Jupyter 筆記本允許就地執行程式碼，連同指示、附注和其他內容。</span><span class="sxs-lookup"><span data-stu-id="54422-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="54422-105">此環境適合用內嵌的說明或量子計算互動式教學課程來撰寫 Q # 程式碼。</span><span class="sxs-lookup"><span data-stu-id="54422-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="54422-106">以下是開始建立您自己的 Q# 筆記本所需的準備工作。</span><span class="sxs-lookup"><span data-stu-id="54422-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="54422-107">IQ# (發音為 i-q-sharp) 是主要供 Jupyter 和 Python 使用的 .NET Core SDK 擴充功能，提供編譯和模擬 Q# 作業的核心功能。</span><span class="sxs-lookup"><span data-stu-id="54422-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="54422-108">在 [Q # Jupyter 筆記本] 中，您只能執行 Q # 程式碼，而且無法從外部主機程式（例如 Python 或 c # 檔案）呼叫作業。</span><span class="sxs-lookup"><span data-stu-id="54422-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="54422-109">如果您的目標是要將外部傳統主機程式與配量程式合併，則此環境不適用。</span><span class="sxs-lookup"><span data-stu-id="54422-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="54422-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="54422-110">Pre-requisites</span></span>

    - <span data-ttu-id="54422-111">[Python](https://www.python.org/downloads/) 3.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="54422-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="54422-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="54422-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="54422-113">.NET Core SDK 3.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="54422-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="54422-114">安裝 `iqsharp` 套件</span><span class="sxs-lookup"><span data-stu-id="54422-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="54422-115">建立 `Hello World` 應用程式來驗證安裝</span><span class="sxs-lookup"><span data-stu-id="54422-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="54422-116">執行下列命令以啟動筆記本伺服器：</span><span class="sxs-lookup"><span data-stu-id="54422-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="54422-117">若要開啟 Jupyter 筆記本，請將命令列所提供的 URL 複製並貼到您的瀏覽器中。</span><span class="sxs-lookup"><span data-stu-id="54422-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="54422-118">使用 Q# 核心建立 Jupyter 筆記本，並將下列程式碼新增至第一個筆記本資料格：</span><span class="sxs-lookup"><span data-stu-id="54422-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="54422-119">執行筆記本的此一資料格：</span><span class="sxs-lookup"><span data-stu-id="54422-119">Run this cell of the notebook:</span></span>

        ![Jupyter 筆記本資料格搭配 Q# 程式碼](~/media/install-guide-jupyter.png)

        <span data-ttu-id="54422-121">您應該會在資料格的輸出中看到 `SayHello`。</span><span class="sxs-lookup"><span data-stu-id="54422-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="54422-122">在 Jupyter 筆記本中執行時，Q# 程式碼會進行編譯，筆記本則會輸出其找到的操作名稱。</span><span class="sxs-lookup"><span data-stu-id="54422-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="54422-123">在新的資料格中，使用命令執行您剛才建立的作業（在模擬器中） `%simulate` ：</span><span class="sxs-lookup"><span data-stu-id="54422-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Jupyter 筆記本資料格搭配 %simulate magic](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="54422-125">您應該會看到訊息印在畫面上，以及您叫用之作業的結果（在這裡，我們會看到空白的元組，因為我們的作業只會傳回 `()` `Unit` 類型）。</span><span class="sxs-lookup"><span data-stu-id="54422-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="54422-126">後續步驟</span><span class="sxs-lookup"><span data-stu-id="54422-126">Next steps</span></span>

<span data-ttu-id="54422-127">您已在慣用環境中安裝了 Quantum Development Kit，因此接下來可以編寫和執行[您的第一個量子程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="54422-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
