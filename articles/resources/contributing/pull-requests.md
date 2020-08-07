---
title: 開啟提取要求
description: 瞭解當您準備好將程式碼或檔提供給 Microsoft Quantum Development Kit 時，如何提交 GitHub 提取要求。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e04e6502e0a6005dfdf0f93450bf3ffd5aaa672
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866922"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="45136-103">開啟提取要求</span><span class="sxs-lookup"><span data-stu-id="45136-103">Opening Pull Requests</span></span> #

<span data-ttu-id="45136-104">配量開發工具組的所有檔都是使用 Git 版本控制系統來管理，其使用 GitHub 上裝載的數個存放庫。</span><span class="sxs-lookup"><span data-stu-id="45136-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="45136-105">搭配使用 Git 和 GitHub 可讓您輕鬆地在「量子開發工具組」上廣泛共同作業。</span><span class="sxs-lookup"><span data-stu-id="45136-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="45136-106">特別是，可以複製或分支任何 Git 存放庫，以建立該存放庫的完全獨立複本。</span><span class="sxs-lookup"><span data-stu-id="45136-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="45136-107">這可讓您使用工具和您偏好的步調來處理您的貢獻。</span><span class="sxs-lookup"><span data-stu-id="45136-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="45136-108">當您準備好時，您可以使用 GitHub 的_提取要求_功能，將您的貢獻包含在我們的存放庫中的要求傳送給我們。</span><span class="sxs-lookup"><span data-stu-id="45136-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="45136-109">每個提取要求的頁面會包含所有變更的詳細資料，這些變更會使您的投稿、您的投稿留言清單，以及其他社區成員可用來提供意見反應和建議的一組審查工具。</span><span class="sxs-lookup"><span data-stu-id="45136-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="45136-110">雖然 Git 的完整教學課程已超出本指南的範圍，但我們可以建議下列連結，以取得有關學習 Git 的更多資源：</span><span class="sxs-lookup"><span data-stu-id="45136-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="45136-111">[瞭解 git](https://www.atlassian.com/git)： Atlassian 中的一組 git 教學課程。</span><span class="sxs-lookup"><span data-stu-id="45136-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="45136-112">[Visual Studio Code 中的版本控制](https://code.visualstudio.com/docs/editor/versioncontrol)：如何使用 Visual Studio Code 作為 Git GUI 的指南。</span><span class="sxs-lookup"><span data-stu-id="45136-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="45136-113">[GitHub 學習實驗室](https://lab.github.com/)：一組使用 Git、GitHub 和相關技術的線上課程。</span><span class="sxs-lookup"><span data-stu-id="45136-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="45136-114">[視覺化 git](https://git-school.github.io/visualizing-git/)：用來視覺化 git 命令如何變更存放庫狀態的互動式工具。</span><span class="sxs-lookup"><span data-stu-id="45136-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="45136-115">[使用 git 進行版本控制 (EPQIS 2016) ](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes))： git 教學課程是面向科學計算。</span><span class="sxs-lookup"><span data-stu-id="45136-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="45136-116">[瞭解 Git 分支](https://learngitbranching.js.org/)：一組互動式分支和重定基底的測驗，協助學習新的 Git 功能。</span><span class="sxs-lookup"><span data-stu-id="45136-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="45136-117">什麼是提取要求？</span><span class="sxs-lookup"><span data-stu-id="45136-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="45136-118">前面說過，要花一些時間來說出提取要求**是**有説明的。</span><span class="sxs-lookup"><span data-stu-id="45136-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="45136-119">使用 Git 時，任何變更都會_表示為認可，以描述_這些變更在這些變更之前與存放庫的狀態有何關聯。</span><span class="sxs-lookup"><span data-stu-id="45136-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="45136-120">我們會經常繪製圖表，其中的認可會繪製成具有先前認可箭號的圓圈。</span><span class="sxs-lookup"><span data-stu-id="45136-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="45136-121">假設您已在名為的_分支_中啟動貢獻 `feature` 。</span><span class="sxs-lookup"><span data-stu-id="45136-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="45136-122">接下來，您的**Microsoft/** 配量分支可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="45136-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![GitHub 中的工作分支](~/media/git-workflow-step0.png)

<span data-ttu-id="45136-124">如果您在本機儲存機制中進行變更，您可以將其他存放庫中的變更_提取_到您的存放庫中，以趕上發生上游的任何變更。</span><span class="sxs-lookup"><span data-stu-id="45136-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![從上游存放庫提取和合併變更](~/media/git-workflow-step1.png)

<span data-ttu-id="45136-126">提取要求的工作方式相同，但相反地：當您開啟提取要求時，您會要求上游存放庫提取您的貢獻。</span><span class="sxs-lookup"><span data-stu-id="45136-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![要求將您的變更提取回原始存放庫](~/media/git-workflow-step2.png)

<span data-ttu-id="45136-128">當您開啟其中一個存放庫的提取要求時，GitHub 會為其他人提供機會，以查看您的變更摘要、對其加上批註，以及提出如何協助做出更好貢獻的建議。</span><span class="sxs-lookup"><span data-stu-id="45136-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![GitHub 中提取要求的螢幕擷取畫面](~/media/pull-request-header.png)

<span data-ttu-id="45136-130">使用此程式可協助我們使用 GitHub 功能來改善貢獻，並為量副程式設計小組維護高品質的產品。</span><span class="sxs-lookup"><span data-stu-id="45136-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="45136-131">如何提出提取要求</span><span class="sxs-lookup"><span data-stu-id="45136-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="45136-132">有兩個主要的方式可建立提取要求。</span><span class="sxs-lookup"><span data-stu-id="45136-132">There are two main ways to make a pull request.</span></span>  
<span data-ttu-id="45136-133">對於只會影響單一檔案的小型變更，GitHub web 介面可以用來完全線上建立提取要求。</span><span class="sxs-lookup"><span data-stu-id="45136-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span> <span data-ttu-id="45136-134">只要流覽至您想要編輯的檔案，然後使用 [編輯] 圖示。</span><span class="sxs-lookup"><span data-stu-id="45136-134">Simply navigate to the file you want to edit and use the edit icon.</span></span>  
<span data-ttu-id="45136-135">對於更複雜的貢獻，將存放庫複製到本機電腦最容易的方式，是先為提取要求做準備。</span><span class="sxs-lookup"><span data-stu-id="45136-135">For more complicated contributions, it's most often easier to clone the repository to your local computer to prepare for a pull request first.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="45136-136">後續步驟</span><span class="sxs-lookup"><span data-stu-id="45136-136">Next steps</span></span> ##

<span data-ttu-id="45136-137">恭喜您使用 Git 來協助您解決量子開發工具組的社區！</span><span class="sxs-lookup"><span data-stu-id="45136-137">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="45136-138">若要深入瞭解如何參與程式碼，請繼續進行下列指南。</span><span class="sxs-lookup"><span data-stu-id="45136-138">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="45136-139">瞭解如何參與程式碼</span><span class="sxs-lookup"><span data-stu-id="45136-139">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
