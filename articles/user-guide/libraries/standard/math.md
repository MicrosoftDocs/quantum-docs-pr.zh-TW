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
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692054"
---
# <a name="classical-mathematical-functions"></a>傳統數學函數 #

這些函數主要用來處理 Q# 內建的資料類型 `Int` 、 `Double` 和 `Range` 。

作業 <xref:Microsoft.Quantum.Intrinsic.Random> 具有簽章 `(Double[] => Int)` 。
它會採用雙精度浮點數作為輸入，並將隨機選取的索引傳回陣列中的 `Int` 。
選取特定索引的機率與該索引的陣列元素值成正比。 n 等於零的陣列元素會被忽略，而且永遠不會傳回其索引。
如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。
