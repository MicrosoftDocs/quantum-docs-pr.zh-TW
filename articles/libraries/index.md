---
title: Quantum Development Kit 程式庫 | Microsoft Docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 7b51945a8aaf937856441cdb10e8a024bf816f88
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442429"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="11b40-102">Q# 程式庫概觀</span><span class="sxs-lookup"><span data-stu-id="11b40-102">Overview of Q# Libraries</span></span>
<span data-ttu-id="11b40-103">Quantum Development Kit 提供了數個程式庫，讓您能夠更輕鬆地在 Q# 中開發量子應用程式。</span><span class="sxs-lookup"><span data-stu-id="11b40-103">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="11b40-104">在文件的這一節中，我們將說明這些程式庫，以及如何在您的程式中加以使用。</span><span class="sxs-lookup"><span data-stu-id="11b40-104">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="11b40-105">[**標準程式庫**](xref:microsoft.quantum.libraries.standard.intro)：本節提供序言，定義 Q# 程式與目標電腦之間的介面，並且定義 Canon，這是一個 Q# 程式庫，可提供撰寫 Q# 程式時所使用的一般用途作業和函式。</span><span class="sxs-lookup"><span data-stu-id="11b40-105">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="11b40-106">[**量子化學程式庫**](xref:microsoft.quantum.chemistry.concepts.intro)：本節說明量子化學程式庫，此程式庫可提供用來載入費米子 Hamiltonian 表示法的資料模型，以及處理這些標記法的量子模擬作業和函式。</span><span class="sxs-lookup"><span data-stu-id="11b40-106">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="11b40-107">[**量子數值程式庫**](xref:microsoft.quantum.numerics.intro)：本節說明量子數值程式庫，此程式庫可提供數學函式主機的實作方式。</span><span class="sxs-lookup"><span data-stu-id="11b40-107">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="11b40-108">它支援整數 (帶正負號和不帶正負號) 和定點表示法。</span><span class="sxs-lookup"><span data-stu-id="11b40-108">It supports integer (signed & unsigned) and fixed-point representations.</span></span>

<span data-ttu-id="11b40-109">您可以從 GitHub 取得程式庫和程式碼範例的來源。</span><span class="sxs-lookup"><span data-stu-id="11b40-109">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span> <span data-ttu-id="11b40-110">如需進一步的資訊，另請參閱[授權](xref:microsoft.quantum.libraries.licensing)一節。</span><span class="sxs-lookup"><span data-stu-id="11b40-110">See also the [licensing](xref:microsoft.quantum.libraries.licensing) section for further information.</span></span> <span data-ttu-id="11b40-111">請注意，套件參考 (「二進位檔」) 也適用於程式庫，可提供另一種在專案中包含程式庫的方式。</span><span class="sxs-lookup"><span data-stu-id="11b40-111">It should be noted that package references ("binaries") are available also for the libraries which offers another way of including the libraries in projects.</span></span> <span data-ttu-id="11b40-112">透過 [nuget](https://nuget.org) 可以很方便地取得這些資源。</span><span class="sxs-lookup"><span data-stu-id="11b40-112">A convenient way of obtaining them is via [nuget](https://nuget.org).</span></span>  