---
title: Microsoft Q# 標準程式庫簡介
description: 了解定義量子程式中所用作業、函式和資料類型的 Microsoft Q# 標準程式庫。
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907149"
---
# <a name="introduction-to-the-q-standard-libraries"></a><span data-ttu-id="8da5a-103">Q# 標準程式庫簡介</span><span class="sxs-lookup"><span data-stu-id="8da5a-103">Introduction to the Q# Standard Libraries</span></span> #

<span data-ttu-id="8da5a-104">Q# 是由各種包含 Q# *標準程式庫*的不同實用作業、函式和使用者定義的類型提供支援。</span><span class="sxs-lookup"><span data-stu-id="8da5a-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="8da5a-105">在[安裝和驗證](xref:microsoft.quantum.install)期間安裝的 [`Microsoft.Quantum.Development.Kit` NuGet 套件](https://www.nuget.org/packages/microsoft.quantum.development.kit) 會提供 Q# 編譯器，以及由目標機器實作的標準程式庫組件。</span><span class="sxs-lookup"><span data-stu-id="8da5a-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="8da5a-106">此[`Microsoft.Quantum.Standard`套件](https://www.nuget.org/packages/microsoft.quantum.standard)可提供跨目標電腦的可攜式 Q# 標準程式庫部分。</span><span class="sxs-lookup"><span data-stu-id="8da5a-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="8da5a-107">在 [API 文件](xref:microsoft.quantum.standardlibsintro)中，Q# 標準程式庫所定義的符號會有更完整、更詳盡的定義。</span><span class="sxs-lookup"><span data-stu-id="8da5a-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="8da5a-108">在下列各節中，我們將概述每部分標準程式庫的最重要功能，並提供有關如何實際使用每項功能的一些內容。</span><span class="sxs-lookup"><span data-stu-id="8da5a-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
