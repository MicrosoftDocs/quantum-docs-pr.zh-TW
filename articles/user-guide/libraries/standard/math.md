---
title: 標準程式庫中的數學運算 Q#
description: 瞭解搭配 Q# 內建資料類型使用的標準程式庫中的傳統數學函數。
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853986"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="acdf2-103">傳統數學函數</span><span class="sxs-lookup"><span data-stu-id="acdf2-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="acdf2-104">這些函數主要用來處理 Q# 內建的資料類型 `Int` 、 `Double` 和 `Range` 。</span><span class="sxs-lookup"><span data-stu-id="acdf2-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="acdf2-105">作業 <xref:Microsoft.Quantum.Intrinsic.Random> 具有簽章 `(Double[] => Int)` 。</span><span class="sxs-lookup"><span data-stu-id="acdf2-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="acdf2-106">它會採用雙精度浮點數作為輸入，並將隨機選取的索引傳回陣列中的 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="acdf2-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="acdf2-107">選取特定索引的機率與該索引的陣列元素值成正比。</span><span class="sxs-lookup"><span data-stu-id="acdf2-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="acdf2-108">n 等於零的陣列元素會被忽略，而且永遠不會傳回其索引。</span><span class="sxs-lookup"><span data-stu-id="acdf2-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="acdf2-109">如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="acdf2-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
