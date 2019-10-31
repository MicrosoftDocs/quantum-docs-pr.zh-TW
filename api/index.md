---
uid: microsoft.quantum.standardlibsintro
title: 適用於 Microsoft Quantum 的 Q# 標準程式庫
description: 適用於 Microsoft Quantum 的 Q# 標準程式庫參考文件
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056954"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="45145-103">Q# 標準程式庫</span><span class="sxs-lookup"><span data-stu-id="45145-103">Q# standard libraries</span></span> #

<span data-ttu-id="45145-104">Q# 是由各種包含 Q#「標準程式庫」  的不同實用作業、函式和使用者定義的類型提供支援。</span><span class="sxs-lookup"><span data-stu-id="45145-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="45145-105">Q# 標準程式庫分為兩大部分：</span><span class="sxs-lookup"><span data-stu-id="45145-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="45145-106">**序言**：定義為目標機器和編譯器一部分的操作和函式，通常採用傳統的原生 .NET 程式碼。</span><span class="sxs-lookup"><span data-stu-id="45145-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="45145-107">一般情況下，不同的目標機器可能會有適用於各個系統的不同序言實作。</span><span class="sxs-lookup"><span data-stu-id="45145-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="45145-108">**Canon**：在定義於序言的邏輯上，Q# 建置中所定義的操作和函式。</span><span class="sxs-lookup"><span data-stu-id="45145-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="45145-109">Canon 實作方式與目標機器無關。</span><span class="sxs-lookup"><span data-stu-id="45145-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="45145-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="45145-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>