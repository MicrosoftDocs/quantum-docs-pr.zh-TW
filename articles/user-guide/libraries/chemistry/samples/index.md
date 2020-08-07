---
title: 量子化學範例應用程式
description: 探索 Microsoft 量子化學程式庫的範例應用程式。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: a0bc79c7fb41069ee7865dbf2f1cfd7851fda32d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869285"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="94eeb-103">量子化學範例</span><span class="sxs-lookup"><span data-stu-id="94eeb-103">Quantum chemistry examples</span></span>

<span data-ttu-id="94eeb-104">在量子化學概念中，我們手動建立了範例費米子 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="94eeb-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="94eeb-105">現在，我們將結合[模擬 Hamiltonian 力學](xref:microsoft.quantum.libraries.standard.algorithms)中所述的化學模擬演算法與 Canon 程式庫中[量子階段估算](xref:microsoft.quantum.libraries.characterization)。</span><span class="sxs-lookup"><span data-stu-id="94eeb-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="94eeb-106">這種組合可讓我們在代表的分子中取得能階的估計值，這是量子電腦上的量子化學其中的一項主要應用。</span><span class="sxs-lookup"><span data-stu-id="94eeb-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="94eeb-107">我們也會依照一些範例逐步大規模地執行量子化學實驗，而不是逐一說明 Hamiltonian 的詞彙。</span><span class="sxs-lookup"><span data-stu-id="94eeb-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="94eeb-108">首先我們要參考的範例，會載入以 [Broombridge 結構描述](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)編碼的化學 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="94eeb-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="94eeb-109">對於過大而無法在[完整狀態模擬器](xref:microsoft.quantum.machines.full-state-simulator)上模擬的分子，我們仍可執行有趣的科學實驗。</span><span class="sxs-lookup"><span data-stu-id="94eeb-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="94eeb-110">例如，我們仍可以[追蹤模擬器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)為目標，來評估執行大型化學模擬的資源成本。</span><span class="sxs-lookup"><span data-stu-id="94eeb-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="94eeb-111">接著，我們就要透過幾個既有的範例，來了解化學模擬程式庫的有趣應用。</span><span class="sxs-lookup"><span data-stu-id="94eeb-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
