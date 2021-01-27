---
title: 開啟提取要求
description: 瞭解當您準備好將程式碼或檔提供給 Microsoft 量子開發工具組時，如何提交 GitHub 提取要求。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.pulls
no-loc:
- Q#
- $$v
ms.openlocfilehash: a936283f3e51da9b97b8145bad3ab765b6423458
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858460"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="6ca86-103">開啟提取要求</span><span class="sxs-lookup"><span data-stu-id="6ca86-103">Opening Pull Requests</span></span> #

<span data-ttu-id="6ca86-104">您可以使用 Git 版本控制系統，利用 GitHub 上裝載的數個存放庫，來管理量子開發工具組的所有檔。</span><span class="sxs-lookup"><span data-stu-id="6ca86-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="6ca86-105">搭配使用 Git 和 GitHub 可讓您輕鬆地廣泛地在量子開發工具組上共同作業。</span><span class="sxs-lookup"><span data-stu-id="6ca86-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="6ca86-106">尤其是，任何 Git 存放庫都可以複製或分叉，以建立該存放庫的完全獨立複本。</span><span class="sxs-lookup"><span data-stu-id="6ca86-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="6ca86-107">這可讓您使用工具和您偏好的步調來處理您的貢獻。</span><span class="sxs-lookup"><span data-stu-id="6ca86-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="6ca86-108">當您準備好時，您可以使用 GitHub 的 _提取要求_ 功能，傳送要求以將您的投稿內容包含在我們的存放庫中。</span><span class="sxs-lookup"><span data-stu-id="6ca86-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="6ca86-109">每個提取要求的頁面都包含所有變更的詳細資料、投稿的評論清單，以及其他社區成員可以用來提供意見反應和建議的一組審核工具。</span><span class="sxs-lookup"><span data-stu-id="6ca86-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="6ca86-110">雖然 Git 的完整教學課程已超出本指南的範圍，但我們可以建議下列連結，以取得有關 learning Git 的更多資源：</span><span class="sxs-lookup"><span data-stu-id="6ca86-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="6ca86-111">[瞭解 git](https://www.atlassian.com/git)： Atlassian 的一組 git 教學課程。</span><span class="sxs-lookup"><span data-stu-id="6ca86-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="6ca86-112">[Visual Studio Code 中的版本控制](https://code.visualstudio.com/docs/editor/versioncontrol)：如何使用 Visual Studio Code 作為 GIT 的 GUI 的指南。</span><span class="sxs-lookup"><span data-stu-id="6ca86-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="6ca86-113">[GitHub 學習實驗室](https://lab.github.com/)：一組使用 Git、GitHub 和相關技術的線上課程。</span><span class="sxs-lookup"><span data-stu-id="6ca86-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="6ca86-114">[視覺化 git](https://git-school.github.io/visualizing-git/)：可哥視化 git 命令如何變更存放庫狀態的互動式工具。</span><span class="sxs-lookup"><span data-stu-id="6ca86-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="6ca86-115">[使用 git 進行版本控制 (EPQIS 2016) ](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes))：以科學計算為導向的 git 教學課程。</span><span class="sxs-lookup"><span data-stu-id="6ca86-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="6ca86-116">[瞭解 Git 分支](https://learngitbranching.js.org/)：一組互動式的分支和重定基底謎題，可協助您學習新的 Git 功能。</span><span class="sxs-lookup"><span data-stu-id="6ca86-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="6ca86-117">什麼是提取要求？</span><span class="sxs-lookup"><span data-stu-id="6ca86-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="6ca86-118">說過上述程式，要花一些時間來說出提取要求 **是** 很有説明的。</span><span class="sxs-lookup"><span data-stu-id="6ca86-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="6ca86-119">使用 Git 時，任何變更都會 _表示為認可，以描述_ 這些變更在這些變更之前如何與存放庫的狀態相關。</span><span class="sxs-lookup"><span data-stu-id="6ca86-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="6ca86-120">我們通常會繪製圖表，其中的認可會繪製為具有上一個認可箭號的圓形。</span><span class="sxs-lookup"><span data-stu-id="6ca86-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="6ca86-121">假設您已在名為的 _分支_ 中開始投稿 `feature` 。</span><span class="sxs-lookup"><span data-stu-id="6ca86-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="6ca86-122">然後，您的 **Microsoft/量子** 分叉可能看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="6ca86-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![GitHub 中的工作分支](~/media/git-workflow-step0.png)

<span data-ttu-id="6ca86-124">如果您在本機存放庫中進行變更，您可以將其他存放庫中的變更 _提取_ 至您的存放庫，以趕上任何發生上游的變更。</span><span class="sxs-lookup"><span data-stu-id="6ca86-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![從上游存放庫提取和合併變更](~/media/git-workflow-step1.png)

<span data-ttu-id="6ca86-126">提取要求的運作方式相同，但相反：當您開啟提取要求時，會要求上游存放庫提取您的投稿。</span><span class="sxs-lookup"><span data-stu-id="6ca86-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![要求將您的變更提取回原始存放庫](~/media/git-workflow-step2.png)

<span data-ttu-id="6ca86-128">當您開啟其中一個存放庫的提取要求時，GitHub 會為該社區中的其他人提供機會來查看您變更的摘要、對其加上批註，以及提出如何協助做出更好貢獻的建議。</span><span class="sxs-lookup"><span data-stu-id="6ca86-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![GitHub 中提取要求的螢幕擷取畫面](~/media/pull-request-header.png)

<span data-ttu-id="6ca86-130">使用此程式可協助我們使用 GitHub 功能來改善投稿內容，並維護量副程式設計社區的高品質產品。</span><span class="sxs-lookup"><span data-stu-id="6ca86-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="6ca86-131">如何提出提取要求</span><span class="sxs-lookup"><span data-stu-id="6ca86-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="6ca86-132">有兩種主要的方式可提出提取要求。</span><span class="sxs-lookup"><span data-stu-id="6ca86-132">There are two main ways to make a pull request.</span></span>  
<span data-ttu-id="6ca86-133">針對只影響單一檔案的小型變更，GitHub web 介面可以用來完全在線上提出提取要求。</span><span class="sxs-lookup"><span data-stu-id="6ca86-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span> <span data-ttu-id="6ca86-134">只要流覽至您想要編輯的檔案，然後使用 [編輯] 圖示。</span><span class="sxs-lookup"><span data-stu-id="6ca86-134">Simply navigate to the file you want to edit and use the edit icon.</span></span>  
<span data-ttu-id="6ca86-135">針對更複雜的投稿，將存放庫複製到您的本機電腦通常會更容易，以便先準備提取要求。</span><span class="sxs-lookup"><span data-stu-id="6ca86-135">For more complicated contributions, it's most often easier to clone the repository to your local computer to prepare for a pull request first.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="6ca86-136">後續步驟</span><span class="sxs-lookup"><span data-stu-id="6ca86-136">Next steps</span></span> ##

<span data-ttu-id="6ca86-137">恭喜您使用 Git 來協助量子開發工具組社區！</span><span class="sxs-lookup"><span data-stu-id="6ca86-137">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="6ca86-138">若要深入瞭解如何參與程式碼，請繼續進行下列指南。</span><span class="sxs-lookup"><span data-stu-id="6ca86-138">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6ca86-139">瞭解如何貢獻程式碼</span><span class="sxs-lookup"><span data-stu-id="6ca86-139">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
