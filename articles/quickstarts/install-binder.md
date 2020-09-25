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
# <a name="develop-with-no-locq-and-binder"></a>使用 Q# 和 Binder 進行開發

您可以使用 Binder，在線上執行並共用您的 Jupyter Notebook。

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>使用 Binder 搭配 Microsoft QDK 範例

將 Binder 自動設定，以使用 Microsoft QDK 範例：

1. 開啟瀏覽器並執行 https://aka.ms/try-qsharp 。
1. 在 **Quantum 開發套件範例** 登陸頁面上，按一下 [Q# 筆記本] 以了解如何使用 IQ# 來撰寫您自己的量子應用程式筆記本。

![QDK 登陸頁面](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>使用 Binder 搭配您自己的筆記本和存放庫

如果您在 GitHub 存放庫中已經有筆記本，可以設定 Binder 來與您的儲存機制搭配使用：

1. 確定存放庫的根目錄中有一個名為「Dockerfile」的檔案。 檔案必須至少包含下列幾行：

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > 您可以在[版本資訊](xref:microsoft.quantum.relnotes)中，確認 IQ# 的目前版本。

    如需關於建立 Dockerfile 的詳細資訊，請參閱 [Dockerfile 參考](https://docs.docker.com/engine/reference/builder/)。

2. 開啟瀏覽器以 [mybinder.org](https://mybinder.org)。
3. 輸入您的存放庫名稱為 **GitHub URL** (例如「MyName/MyRepo」)，然後按一下 [啟動]。

![MyBinder 表單](~/media/mybinder.png)
    
## <a name="next-steps"></a>後續步驟

既然您已設定 Binder 環境，您可以撰寫並執行[您的第一個配量程式](xref:microsoft.quantum.quickstarts.qrng)。
