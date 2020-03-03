---
title: 量子機器學習套件簡介 | Microsoft Docs
description: 量子機器學習套件簡介
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
ms.openlocfilehash: 7f22d5d3212890abc764f88693937b534466170f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907846"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="cb570-103">量子機器學習程式庫簡介</span><span class="sxs-lookup"><span data-stu-id="cb570-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="cb570-104">量子機器學習程式庫是以 Q# 撰寫的 API，可讓您執行混合式量子/傳統機器學習實驗。</span><span class="sxs-lookup"><span data-stu-id="cb570-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="cb570-105">程式庫讓您能夠：</span><span class="sxs-lookup"><span data-stu-id="cb570-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="cb570-106">載入您自己的資料，並使用量子模擬器來分類</span><span class="sxs-lookup"><span data-stu-id="cb570-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="cb570-107">使用範例和教學課程來了解量子機器學習的領域</span><span class="sxs-lookup"><span data-stu-id="cb570-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="cb570-108">此效能可能比目前的傳統機器學習架構低 (請記住，所有項目都會在已耗用大量運算資源的模擬量子裝置上執行)。</span><span class="sxs-lookup"><span data-stu-id="cb570-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="cb570-109">本文件的目的是：</span><span class="sxs-lookup"><span data-stu-id="cb570-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="cb570-110">簡介適用於混合式量子/傳統學習的機器學習工具 (以 Q\# 撰寫)。</span><span class="sxs-lookup"><span data-stu-id="cb570-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="cb570-111">介紹機器學習概念，尤其是其如何運用在量子線路中心分類器 (也稱為量子循序分類器)。</span><span class="sxs-lookup"><span data-stu-id="cb570-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="cb570-112">提供一組基本概念教學課程，協助您開始使用程式庫所提供的工具。</span><span class="sxs-lookup"><span data-stu-id="cb570-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="cb570-113">討論這類分類器的訓練和驗證方法，以及其如何轉譯為程式庫所提供的特定 Q\# 作業。</span><span class="sxs-lookup"><span data-stu-id="cb570-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="cb570-114">此程式庫中所執行的模型是以[線路中心量子分類器](https://arxiv.org/abs/1804.00633)中所呈現的量子傳統訓練配置為基礎</span><span class="sxs-lookup"><span data-stu-id="cb570-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
