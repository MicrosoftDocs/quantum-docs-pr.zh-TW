---
title: 使用 Q# 和 Binder 進行開發
description: 了解如何使用 Binder 建立 Q# 應用程式。
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836524"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="075c7-103">使用 Q# 和 Binder 進行開發</span><span class="sxs-lookup"><span data-stu-id="075c7-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="075c7-104">您可以使用 Binder，在線上執行並共用您的 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="075c7-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="075c7-105">使用 Binder 搭配 Microsoft QDK 範例</span><span class="sxs-lookup"><span data-stu-id="075c7-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="075c7-106">將 Binder 自動設定，以使用 Microsoft QDK 範例：</span><span class="sxs-lookup"><span data-stu-id="075c7-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="075c7-107">開啟瀏覽器並執行 https://aka.ms/try-qsharp 。</span><span class="sxs-lookup"><span data-stu-id="075c7-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="075c7-108">在 **Quantum 開發套件範例** 登陸頁面上，按一下 [Q# 筆記本] 以了解如何使用 IQ# 來撰寫您自己的量子應用程式筆記本。</span><span class="sxs-lookup"><span data-stu-id="075c7-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![QDK 登陸頁面](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="075c7-110">使用 Binder 搭配您自己的筆記本和存放庫</span><span class="sxs-lookup"><span data-stu-id="075c7-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="075c7-111">如果您在 GitHub 存放庫中已經有筆記本，可以設定 Binder 來與您的儲存機制搭配使用：</span><span class="sxs-lookup"><span data-stu-id="075c7-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="075c7-112">確定存放庫的根目錄中有一個名為「Dockerfile」的檔案。</span><span class="sxs-lookup"><span data-stu-id="075c7-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="075c7-113">檔案必須至少包含下列幾行：</span><span class="sxs-lookup"><span data-stu-id="075c7-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="075c7-114">您可以在[版本資訊](xref:microsoft.quantum.relnotes)中，確認 IQ# 的目前版本。</span><span class="sxs-lookup"><span data-stu-id="075c7-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="075c7-115">如需關於建立 Dockerfile 的詳細資訊，請參閱 [Dockerfile 參考](https://docs.docker.com/engine/reference/builder/)。</span><span class="sxs-lookup"><span data-stu-id="075c7-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="075c7-116">開啟瀏覽器以 [mybinder.org](https://mybinder.org)。</span><span class="sxs-lookup"><span data-stu-id="075c7-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="075c7-117">輸入您的存放庫名稱為 **GitHub URL** (例如「MyName/MyRepo」)，然後按一下 [啟動]。</span><span class="sxs-lookup"><span data-stu-id="075c7-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![MyBinder 表單](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="075c7-119">後續步驟</span><span class="sxs-lookup"><span data-stu-id="075c7-119">Next steps</span></span>

<span data-ttu-id="075c7-120">既然您已設定 Binder 環境，您可以撰寫並執行[您的第一個配量程式](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="075c7-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
