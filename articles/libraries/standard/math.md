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
# <a name="classical-mathematical-functions"></a>傳統數學函式 #

這些函式主要是用來處理 Q # 內建資料類型 `Int`、`Double`和 `Range`。

<xref:microsoft.quantum.intrinsic.random> 作業的簽章 `(Double[] => Int)`。
它會採用 double 的陣列做為輸入，並將隨機選取的索引當做 `Int`傳回陣列。
選取特定索引的機率會與該索引的 array 元素值成正比。 會忽略等於零的 n 個陣列元素，而且永遠不會傳回其索引。
如果任何陣列元素小於零，或如果沒有陣列元素大於零，則作業會失敗。