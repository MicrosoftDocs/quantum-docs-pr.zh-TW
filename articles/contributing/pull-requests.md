---
title: 開啟提取要求 |Microsoft Docs
description: 開啟提取要求
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: d70a0a0319d14cfdae4910b897733d77b236f2f9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183721"
---
# <a name="opening-pull-requests"></a>開啟提取要求 #

配量開發工具組的所有檔都是使用 Git 版本控制系統來管理，其使用 GitHub 上裝載的數個存放庫。
搭配使用 Git 和 GitHub 可讓您輕鬆地在「量子開發工具組」上廣泛共同作業。
特別是，可以複製或分支任何 Git 存放庫，以建立該存放庫的完全獨立複本。
這可讓您使用工具和您偏好的步調來處理您的貢獻。

當您準備好時，您可以使用 GitHub 的_提取要求_功能，將您的貢獻包含在我們的存放庫中的要求傳送給我們。
每個提取要求的頁面會包含所有變更的詳細資料，這些變更會使您的投稿、您的投稿留言清單，以及其他社區成員可用來提供意見反應和建議的一組審查工具。

> [!NOTE]
> 雖然 Git 的完整教學課程已超出本指南的範圍，但我們可以建議下列連結，以取得有關學習 Git 的更多資源：
>
> - [瞭解 git](https://www.atlassian.com/git)： Atlassian 中的一組 git 教學課程。
> - [Visual Studio Code 中的版本控制](https://code.visualstudio.com/docs/editor/versioncontrol)：如何使用 Visual Studio Code 作為 Git GUI 的指南。
> - [GitHub 學習實驗室](https://lab.github.com/)：一組使用 Git、GitHub 和相關技術的線上課程。
> - [視覺化 git](https://git-school.github.io/visualizing-git/)：用來視覺化 git 命令如何變更存放庫狀態的互動式工具。
> - [使用 git 進行版本控制（EPQIS 2016）](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes))：以科學計算為導向的 git 教學課程。
> - [瞭解 Git 分支](https://learngitbranching.js.org/)：一組互動式分支和重定基底的測驗，協助學習新的 Git 功能。

## <a name="what-is-a-pull-request"></a>什麼是提取要求？ ##

前面說過，要花一些時間來說出提取要求**是**有説明的。
使用 Git 時，任何變更都會_表示為認可，以描述_這些變更在這些變更之前與存放庫的狀態有何關聯。
我們會經常繪製圖表，其中的認可會繪製成具有先前認可箭號的圓圈。

假設您已在名為 `feature`的_分支_中啟動貢獻。
接下來，您的**Microsoft/** 配量分支可能如下所示：

![](~/media/git-workflow-step0.png)

如果您在本機儲存機制中進行變更，您可以將其他存放庫中的變更_提取_到您的存放庫中，以趕上發生上游的任何變更。

![](~/media/git-workflow-step1.png)

提取要求的工作方式相同，但相反地：當您開啟提取要求時，您會要求上游存放庫提取您的貢獻。

![](~/media/git-workflow-step2.png)

當您開啟其中一個存放庫的提取要求時，GitHub 會為其他人提供機會，以查看您的變更摘要、對其加上批註，以及提出如何協助做出更好貢獻的建議。

![](~/media/pull-request-header.png)

使用此程式可協助我們使用 GitHub 功能來改善貢獻，並為量副程式設計小組維護高品質的產品。

## <a name="how-to-make-a-pull-request"></a>如何提出提取要求 ##

有兩個主要的方式可建立提取要求。
對於只會影響單一檔案的小型變更，GitHub web 介面可以用來完全線上建立提取要求。
如需更複雜的貢獻，最好先使用本機電腦來準備提取要求。

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a>後續步驟 ##

恭喜您使用 Git 來協助您解決量子開發工具組的社區！
若要深入瞭解如何參與程式碼，請繼續進行下列指南。

> [!div class="nextstepaction"]
> [瞭解如何參與程式碼](xref:microsoft.quantum.contributing.code)
