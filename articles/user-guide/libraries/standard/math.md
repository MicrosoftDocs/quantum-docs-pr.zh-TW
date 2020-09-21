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
# <a name="classical-mathematical-functions"></a>傳統數學函數 #

這些函數主要用來處理 Q# 內建的資料類型 `Int` 、 `Double` 和 `Range` 。

作業 <xref:microsoft.quantum.intrinsic.random> 具有簽章 `(Double[] => Int)` 。
它會採用雙精度浮點數作為輸入，並將隨機選取的索引傳回陣列中的 `Int` 。
選取特定索引的機率與該索引的陣列元素值成正比。 n 等於零的陣列元素會被忽略，而且永遠不會傳回其索引。
如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。
