---
title: 'Q # 標準程式庫-數學 |Microsoft Docs'
description: 'Q # 標準程式庫-數學'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184452"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="2e2a3-103">傳統數學函式</span><span class="sxs-lookup"><span data-stu-id="2e2a3-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="2e2a3-104">這些函式主要是用來處理 Q # 內建資料類型 `Int`、`Double`和 `Range`。</span><span class="sxs-lookup"><span data-stu-id="2e2a3-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="2e2a3-105"><xref:microsoft.quantum.intrinsic.random> 作業的簽章 `(Double[] => Int)`。</span><span class="sxs-lookup"><span data-stu-id="2e2a3-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="2e2a3-106">它會採用 double 的陣列做為輸入，並將隨機選取的索引當做 `Int`傳回陣列。</span><span class="sxs-lookup"><span data-stu-id="2e2a3-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="2e2a3-107">選取特定索引的機率會與該索引的 array 元素值成正比。</span><span class="sxs-lookup"><span data-stu-id="2e2a3-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="2e2a3-108">會忽略等於零的 n 個陣列元素，而且永遠不會傳回其索引。</span><span class="sxs-lookup"><span data-stu-id="2e2a3-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="2e2a3-109">如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="2e2a3-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>