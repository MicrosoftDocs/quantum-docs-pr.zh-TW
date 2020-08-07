---
title: 標準程式庫中的數學運算 Q#
description: 瞭解 Q# 用於內建資料類型之標準程式庫中的傳統數學函數。
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868418"
---
# <a name="classical-mathematical-functions"></a>傳統數學函式 #

這些函式主要是用來處理 Q# 內建的資料類型 `Int` 、 `Double` 和 `Range` 。

作業 <xref:microsoft.quantum.intrinsic.random> 具有簽章 `(Double[] => Int)` 。
它會採用 double 的陣列做為輸入，並將隨機選取的索引以形式傳回至陣列 `Int` 。
選取特定索引的機率會與該索引的 array 元素值成正比。 會忽略等於零的 n 個陣列元素，而且永遠不會傳回其索引。
如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。
