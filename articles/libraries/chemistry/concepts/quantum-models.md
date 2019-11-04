---
title: 電子系統的量子模型 |Microsoft Docs
description: 電子系統的量子模型概念檔
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 45d134333c8a3c8937d206cb0a4a9cc6101a85df
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184146"
---
# <a name="quantum-models-for-electronic-systems"></a>電子系統的量子模型

為了模擬電子系統，我們必須先指定 Hamiltonian，這可以透過上述的標準量化程式來找到。
具體而言，針對 $N _e $ electrons with momenta $p _i $ （三個維度），以及大量 $m _e $ 和 position 向量 $x _i $，以及在 nuclei 加上費用 $Z _k e $ at $y _k $，Hamiltonian 運算子會讀取 \begin{equation} \hat{H} = \sum\_{i = 1} ^ {N\_e} \frac{\hat{p}\_i ^ 2} {2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_i-\hat{x}\_j |}-\sum\_{i，k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |}+ \frac{1}{2} \ sum_ {k\ne k '} \frac{Z\_kZ\_{k '} e ^ 2} {| y\_k-y\_k ' |}。 \label{eq： Ham} \end{equation} momenta operators $ \hat{p}\_i ^ 2 $ 可以在實際空間中視為拉普拉斯分配運算子，例如 $ \hat{p}\_i ^ 2 =-\partial\_{x\_i} ^ 2-\partial\_{y\_i} ^ 2-\partial\_{z\_i} ^ 2 $。
在這裡，我們將簡化假設分子的 nuclei 為 rest。
這稱為「正式 Oppenheimer 近似值」，而且通常會對 $ \hat{H} $ 的低能量能源範圍有效，因為 electron 大量約為 $ 1/1836 $ proton 的品質。
藉由寫出 $N\_e $ electrons 之系統的能源，並套用配量[Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)中所述的標準量化處理常式，可以輕鬆地找到此 Hamiltonian 運算子。

為了建造 $e ^ {-i\hat {H} t} $ 的單一矩陣標記法，我們必須以矩陣表示運算子 $ \hat{H} $。
為此，我們需要選擇座標系統或基礎來表示中的問題。
例如，如果 $ \ psi_j $ 是 $N _e $ electrons 的一組正向基礎函數，則我們可以定義矩陣

\begin{equation} H\_{i，j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \infty \psi ^ {\*}\_i （x\_1） \hat{H} \psi\_j （x\_2） \dd ^ 3 倍\_1 \dd ^ 3 倍\_2. \ label {eq： discreteHam} \end{equation}

雖然準則中的運算子 $ \hat{H} $ 未系結，且不會在有限維度空間上作用，但具有元素的矩陣 $H\_\{i，j\}$）。
這表示錯誤的產生是因為挑選太小的基礎集。不過，挑選一個大型的，可以讓模擬化學 dynamics 不切實際。
基於這個理由，選擇可簡潔呈現問題的基礎，對於解決電子結構問題非常重要。

您可以使用許多適當的基底，並選擇適合此問題的良好基礎，這就是量子化學的一大藝術。
可能是最簡單的這類基礎集，也就是 Slater-Orbitals （停止），也就是 Schrödinger （即 $ eigenfunctions $ 的 \hat{H}）適用于 hydrogen 的原子的（orthogonalized）解決方案。
您可以使用其他基礎集，例如平面波浪或實際空間 orbitals，以取得更多詳細資料，我們會將好奇的讀者視為標準文字「[分子電子結構理論](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572)」 Helgaker。

雖然上述模型中所使用的狀態看起來可能是任意的，但配量機制會對可在本質上找到的狀態施加限制。
特別是，所有有效的電子配量狀態在 electron 標籤的交換下都必須是反對稱的。
也就是說，如果 $ \psi （x_1，x_2） $ 是兩個 electrons 的聯合配量狀態的 wave 函式，則必須要有 $ $ \psi （x_1，x_2） =-\psi （x_2，x_1）。
$ $ Pauli 排除原則，這種情況會禁止兩個 electrons 處於相同的配量狀態，fascinatingly，這項法則的直接結果就是可以從事實中 intuited，因為我們交換了兩個位于相同位置 $ electrons （x_1，x_1） \psi \mapsto 的 \psi （x_1，x_1） \ne-\psi （x_1，x_1） $，除非 $ \psi （x_1，x_1） = 0 $。
因此，您必須選擇初始狀態來遵守此反對稱屬性，而且永遠不會有兩個 electrons 處於相同的狀態。
這對電子結構而言非常重要，因為它會禁止多個 electrons 處於相同的狀態，然後讓量子電腦使用單一的配量來儲存指定之量子狀態中的 electrons 數目。

雖然可以藉由分隔這些狀態來模擬量子電腦上的配量機制，但欄位中大部分的工作都已 eschewed 這種方法，因為它需要許多 qubits 來儲存狀態，而且需要複雜的狀態準備程式來準備反對稱初始狀態。
幸好，您可以從不同的觀點來觀看模擬問題，以 sidestepped 這些問題。
