---
title: 量子化學程式庫簡介
description: 了解 Microsoft 量子化學程式庫，以及如何使用該程式庫來模擬量子電腦上的電子結構問題。
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3fa606600db1641b9f8b86ccefebb7681f181b92
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847476"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a><span data-ttu-id="0d358-103">量子化學程式庫簡介</span><span class="sxs-lookup"><span data-stu-id="0d358-103">Introduction to the Quantum Chemistry Library</span></span>

<span data-ttu-id="0d358-104">實體系統的模擬在量子運算的領域一直扮演著重要角色。</span><span class="sxs-lookup"><span data-stu-id="0d358-104">Simulation of physical systems has long played a central role in quantum computing.</span></span>  <span data-ttu-id="0d358-105">這是因為一般普遍認為量子力學難以在量子電腦上進行模擬，這意味著，模擬系統的複雜度會隨著量子系統的大小呈指數增長。</span><span class="sxs-lookup"><span data-stu-id="0d358-105">This is because quantum dynamics are widely believed to be intractable to simulate on quantum computers, meaning that the complexity of simulating the system scales exponentially with the size of the quantum system in question.</span></span>  <span data-ttu-id="0d358-106">模擬化學和教材科學的問題，可能仍是最令人印象深刻的量子運算應用，且讓我們能夠探索至今仍沒有能力測量或模擬的化學反應機制。</span><span class="sxs-lookup"><span data-stu-id="0d358-106">Simulating problems in chemistry and material science remains perhaps the most evocative application of quantum computing and would allow us to probe chemical reaction mechanisms that hitherto were beyond our ability to measure or simulate.</span></span>  <span data-ttu-id="0d358-107">這也讓我們得以模擬相互關聯的電子資料，例如高溫超導體。</span><span class="sxs-lookup"><span data-stu-id="0d358-107">It would also allow us to simulate correlated electronic materials such as high-temperature superconductors.</span></span> <span data-ttu-id="0d358-108">這個領域的應用範圍很廣。</span><span class="sxs-lookup"><span data-stu-id="0d358-108">The list of applications in this space is vast.</span></span>

<span data-ttu-id="0d358-109">本文件的目的是要簡扼介紹如何在量子電腦上模擬電子結構問題，以協助讀者了解 Hamiltonian 模擬程式庫的多種層面在此領域中扮演的角色。</span><span class="sxs-lookup"><span data-stu-id="0d358-109">The purpose of this documentation is to provide a concise introduction to simulating electronic structure problems on quantum computers in order to help the reader understand the role that many aspects of the Hamiltonian simulation library play within the space.</span></span>  <span data-ttu-id="0d358-110">首先我們會簡單介紹量子機制，然後討論如何據以進行電子系統的模型化。</span><span class="sxs-lookup"><span data-stu-id="0d358-110">We begin with a brief introduction to quantum mechanics and then proceed to discuss how electronic systems are modeled in it.</span></span>  <span data-ttu-id="0d358-111">接著，我們將討論如何使用量子電腦來模擬這類量子力學。</span><span class="sxs-lookup"><span data-stu-id="0d358-111">We will then discuss how such quantum dynamics can be emulated using a quantum computer.</span></span>  <span data-ttu-id="0d358-112">然後，我們將討論兩種用來將量子力學編譯為基本閘道序列的方法：Trotter-Suzuki 分解和量子位元化。</span><span class="sxs-lookup"><span data-stu-id="0d358-112">Once this is complete we will discuss two methods used to compile the quantum dynamics to sequences of elementary gates: Trotter-Suzuki decompositions and qubitization.</span></span>
