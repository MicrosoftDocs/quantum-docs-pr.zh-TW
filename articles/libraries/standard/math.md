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
# <a name="classical-mathematical-functions"></a>傳統數學函式 #

這些函式主要是用來處理 Q # 內建資料類型 `Int`、`Double`和 `Range`。

<xref:microsoft.quantum.intrinsic.random> 作業的簽章 `(Double[] => Int)`。
它會採用 double 的陣列做為輸入，並將隨機選取的索引當做 `Int`傳回陣列。
選取特定索引的機率會與該索引的 array 元素值成正比。 會忽略等於零的 n 個陣列元素，而且永遠不會傳回其索引。
如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。
