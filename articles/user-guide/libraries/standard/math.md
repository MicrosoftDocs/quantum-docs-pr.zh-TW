---
title: 標準程式庫中的數學運算 Q#
description: 瞭解搭配 Q# 內建資料類型使用的標準程式庫中的傳統數學函數。
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833600"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="8143d-103">傳統數學函數</span><span class="sxs-lookup"><span data-stu-id="8143d-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="8143d-104">這些函數主要用來處理 Q# 內建的資料類型 `Int` 、 `Double` 和 `Range` 。</span><span class="sxs-lookup"><span data-stu-id="8143d-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="8143d-105">作業 <xref:microsoft.quantum.intrinsic.random> 具有簽章 `(Double[] => Int)` 。</span><span class="sxs-lookup"><span data-stu-id="8143d-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="8143d-106">它會採用雙精度浮點數作為輸入，並將隨機選取的索引傳回陣列中的 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="8143d-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="8143d-107">選取特定索引的機率與該索引的陣列元素值成正比。</span><span class="sxs-lookup"><span data-stu-id="8143d-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="8143d-108">n 等於零的陣列元素會被忽略，而且永遠不會傳回其索引。</span><span class="sxs-lookup"><span data-stu-id="8143d-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="8143d-109">如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="8143d-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
