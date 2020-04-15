---
title: 量子數值程式庫簡介 | Microsoft Docs
description: 量子數值程式庫簡介
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: efd1a712616534ac281433fc008f0983271881d7
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2020
ms.locfileid: "73442450"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="64372-103">量子數值程式庫簡介</span><span class="sxs-lookup"><span data-stu-id="64372-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="64372-104">許多量子演算法都依賴 [Oracle](xref:microsoft.quantum.concepts.oracles) 來進行輸入疊加上的數學函式求解。</span><span class="sxs-lookup"><span data-stu-id="64372-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="64372-105">例如，Shor 演算法的主要元件會針對固定 $a$、因數 $N$ 的數字，以及 $x$ (所有 $2n$ 位元字串的均勻疊加中的 $2n$ 量子位元整數)，進行 $f(x) = a^x\operatorname{mod} N$ 求解。</span><span class="sxs-lookup"><span data-stu-id="64372-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="64372-106">若要在實際的量子電腦上執行 Shor 演算法，則必須根據目標電腦的原生作業來撰寫此函式。</span><span class="sxs-lookup"><span data-stu-id="64372-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="64372-107">使用 $x$ 的二進位表示法 (以 $x_i$ 標記從最低有效位元算起的第 $i$ 個位元)，可以將 $f(x)$ 撰寫為 (x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$。</span><span class="sxs-lookup"><span data-stu-id="64372-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="64372-108">進而可將其撰寫為數項 $a^{2^i x_i}=(a^{2^i})^{x_i}$ 的乘積 (mod N)。</span><span class="sxs-lookup"><span data-stu-id="64372-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="64372-109">因此可使用一連串乘以 $a^{2^i}$ 的 $2n$ (模數) 乘法運算 (以 $x_i$ 不為零為條件) 來實作函式 $f(x)$。</span><span class="sxs-lookup"><span data-stu-id="64372-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="64372-110">在執行演算法之前，常數 $a^{2^i}$ 可預先進行計算並約減模數 N。</span><span class="sxs-lookup"><span data-stu-id="64372-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="64372-111">這一連串的受控模數乘法運算可進一步簡化：每個乘法運算都可以使用一連串的 $n$ 受控模數加法運算來執行；而每個模數加法運算都可以從一個正則加法和一個比較子建立。</span><span class="sxs-lookup"><span data-stu-id="64372-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="64372-112">假設實際實作時必須達成這麼多步驟，那麼從一開始就有這類功能會非常有用。</span><span class="sxs-lookup"><span data-stu-id="64372-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="64372-113">這就是 Quantum Development Kit 為何提供各種數值功能的支援。</span><span class="sxs-lookup"><span data-stu-id="64372-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="64372-114">功能</span><span class="sxs-lookup"><span data-stu-id="64372-114">Functionality</span></span>

<span data-ttu-id="64372-115">除了到目前為止所提到的整數算術以外，數值程式庫還提供：</span><span class="sxs-lookup"><span data-stu-id="64372-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

 - <span data-ttu-id="64372-116">以一或兩個量子整數數字作為輸入的 (不) 帶正負號整數功能 (乘、平方、帶餘數除法、逆轉換等)</span><span class="sxs-lookup"><span data-stu-id="64372-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
 - <span data-ttu-id="64372-117">以一或兩個量子固定點數字作為輸入的定點功能 (加 / 減、乘、評分、1/x、多項式求解)</span><span class="sxs-lookup"><span data-stu-id="64372-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="64372-118">開始使用</span><span class="sxs-lookup"><span data-stu-id="64372-118">Getting started</span></span>

<span data-ttu-id="64372-119">若要開始使用數值程式庫，請參閱[安裝指南](xref:microsoft.quantum.numerics.installation)以及[使用數值程式庫](xref:microsoft.quantum.numerics.usage)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="64372-119">To get started with the Numerics Library, check out the [installation guide](xref:microsoft.quantum.numerics.installation) and more information on [using the Numerics Library](xref:microsoft.quantum.numerics.usage).</span></span>
