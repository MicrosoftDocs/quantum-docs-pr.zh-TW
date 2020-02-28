---
title: 'Q # 標準程式庫中的數學運算'
description: '瞭解用於內建資料類型的 Q # 標準程式庫中的傳統數學函數。'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906146"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="5bab4-103">傳統數學函式</span><span class="sxs-lookup"><span data-stu-id="5bab4-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="5bab4-104">這些函式主要是用來處理 Q # 內建資料類型 `Int`、`Double`和 `Range`。</span><span class="sxs-lookup"><span data-stu-id="5bab4-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="5bab4-105"><xref:microsoft.quantum.intrinsic.random> 作業的簽章 `(Double[] => Int)`。</span><span class="sxs-lookup"><span data-stu-id="5bab4-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="5bab4-106">它會採用 double 的陣列做為輸入，並將隨機選取的索引當做 `Int`傳回陣列。</span><span class="sxs-lookup"><span data-stu-id="5bab4-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="5bab4-107">選取特定索引的機率會與該索引的 array 元素值成正比。</span><span class="sxs-lookup"><span data-stu-id="5bab4-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="5bab4-108">會忽略等於零的 n 個陣列元素，而且永遠不會傳回其索引。</span><span class="sxs-lookup"><span data-stu-id="5bab4-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="5bab4-109">如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。</span><span class="sxs-lookup"><span data-stu-id="5bab4-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
