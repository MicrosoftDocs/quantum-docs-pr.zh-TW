---
title: 量子數值程式庫簡介 | Microsoft Docs
description: 量子數值程式庫簡介
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442450"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>量子數值程式庫簡介

許多量子演算法都依賴 [Oracle](xref:microsoft.quantum.concepts.oracles) 來進行輸入疊加上的數學函式求解。
例如，Shor 演算法的主要元件會針對固定 $a$、因數 $N$ 的數字，以及 $x$ (所有 $2n$ 位元字串的均勻疊加中的 $2n$ 量子位元整數)，進行 $f(x) = a^x\operatorname{mod} N$ 求解。

若要在實際的量子電腦上執行 Shor 演算法，則必須根據目標電腦的原生作業來撰寫此函式。
使用 $x$ 的二進位表示法 (以 $x_i$ 標記從最低有效位元算起的第 $i$ 個位元)，可以將 $f(x)$ 撰寫為 (x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$。
進而可將其撰寫為數項 $a^{2^i x_i}=(a^{2^i})^{x_i}$ 的乘積 (mod N)。 因此可使用一連串乘以 $a^{2^i}$ 的 $2n$ (模數) 乘法運算 (以 $x_i$ 不為零為條件) 來實作函式 $f(x)$。 在執行演算法之前，常數 $a^{2^i}$ 可預先進行計算並約減模數 N。

這一連串的受控模數乘法運算可進一步簡化：每個乘法運算都可以使用一連串的 $n$ 受控模數加法運算來執行；而每個模數加法運算都可以從一個正則加法和一個比較子建立。


假設實際實作時必須達成這麼多步驟，那麼從一開始就有這類功能會非常有用。
這就是 Quantum Development Kit 為何提供各種數值功能的支援。


## <a name="functionality"></a>功能

除了到目前為止所提到的整數算術以外，數值程式庫還提供：

 - 以一或兩個量子整數數字作為輸入的 (不) 帶正負號整數功能 (乘、平方、帶餘數除法、逆轉換等)
 - 以一或兩個量子固定點數字作為輸入的定點功能 (加 / 減、乘、評分、1/x、多項式求解)

## <a name="getting-started"></a>開始使用

若要開始使用數值程式庫，請參閱[安裝指南](xref:microsoft.quantum.numerics.installation)以及[使用數值程式庫](xref:microsoft.quantum.numerics.usage)的詳細資訊。
