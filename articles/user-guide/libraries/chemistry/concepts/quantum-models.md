---
title: 電子系統的量子模型
description: 瞭解如何使用量子模型模擬分子電子系統。
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.quantummodels
no-loc:
- Q#
- $$v
ms.openlocfilehash: c12ab277f06bed61991a26af96953ccdbf72b642
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856229"
---
# <a name="quantum-models-for-electronic-systems"></a>電子系統的量子模型

為了模擬電子系統，我們必須先指定 Hamiltonian，您可以在上面所述的標準量化程式中找到。
具體來說，針對 $N _e $ 電子 with momenta $p _i $ (在三個維度中) 和大量 $m _e $ 和位置向量 $x _i $ 和 nuclei，其費用 $Z _k e $ 的位置 $y _k $，Hamiltonian 運算子會讀取 \begin{equation} \hat{H} = \sum \_ {i = 1} ^ {N \_ e} \frac{\hat{p} \_ i ^ 2} {2m \_ e} + \frac {1} {2} \sum \_ {i\ne j} \frac{e ^ 2} {| \hat{x} \_ i-\hat{x} \_ j |}-\sum \_ {i，k} \frac{Z \_ ke ^ 2} {| \hat{x} \_ i-{y} \_ k |}+ \frac {1} {2} \ sum_ {k\ne k '} \frac{Z \_ kZ \_ {k '} e ^ 2} {| y \_ k-y \_ k ' |}。 \label{eq： Ham} \end{equation} momenta 運算子 $ \hat{p} \_ i ^ 2 $ 可以在真實空間中以拉普拉斯分配運算子的形式來查看，也就是 $ \hat{p} \_ i ^ 2 =-\partial {x i} ^ 2-\partial {y i} ^ 2 \_ \_ \_ \_ -\partial \_ {z \_ i} ^ 2 $。
在這裡，我們已經簡化了分子的 nuclei 工作。
這就是所謂的 Born-Oppenheimer 近似值，它通常適用于 $ \hat{H} $ 的低能源能源範圍，因為 electron 品質大約是 $ 1/1836 $ proton 的品質。
藉由寫出 $N \_ e $ 電子系統的能源，並套用 [量子 Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)中所述的標準量化程式，即可輕鬆找到這個 Hamiltonian 操作員。

為了針對 $e ^ {-i\hat {H} t} $ 建立單一矩陣標記法，我們必須將運算子 $ \hat{H} $ 表示為矩陣。
為此，我們必須選擇座標系統或基礎來代表中的問題。
例如，如果 $ \ psi_j $ 是 $N _e $ 電子的一組正向基礎函數，則可以定義矩陣

\begin{equation} H \_ {i，j} = \int \_ {-\infty} ^ \infty\int \_ {-\infty} ^ \infty \psi ^ { \* } \_ i (x \_ 1) \hat{H} \psi \_ j (x \_ 2) \dd ^ 3 \_ ： 3 ^ \_ 2. \ label {eq： \dd} discreteHam

雖然在主體中，運算子 $ \hat{H} $ 是未系結的，且不會在有限的維度空間上運作，但上面的 $H \_ \{ i，j $ 的元素的矩陣則有 \} 。
這表示，藉由挑選太小的基礎集來產生錯誤;不過，挑選大型基礎可以模擬化學 dynamics 的實際情況。
基於這個理由，選擇可精確呈現問題的基礎對於解決電子結構問題很重要。

有許多適合的基底可供使用，而選擇適當的基礎來滿足問題，就是量子化學的最大藝術。
這可能是最簡單的這類基礎集合，也就是 Slater 型別 Orbitals (停止) ， (orthogonalized) 解決方案加入薛丁格方程式 (例如 eigenfunctions of $ \hat{H} $) 適用于 hydrogen 之類的原子。
您可以使用其他基礎集合（例如，平面波浪或 orbitals），以取得更多詳細資料，我們會透過 Helgaker 將好奇的讀者指向標準文字「 [分子 Electronic-Structure 理論](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) 」。

雖然上述模型中所使用的狀態看起來可能是任意的，但量子機制會對可在本質上找到的狀態施加限制。
尤其是，所有有效的電子量子狀態在 electron 標籤的交換下都必須是反對稱的。
也就是說，如果 $ \psi (x_1，x_2) $ 是否為兩個電子的聯合量子狀態的 wave 函式，則必須有該 $ $ \psi (x_1，x_2) =-\psi (x_2 x_1) 。
$ $ Pauli 排除原則會禁止兩個電子在相同的量子狀態中，fascinatingly，這條法則的直接結果 intuited 來源，因為我們交換兩個電子位於相同位置 $ \psi (x_1，x_1) \mapsto \psi (x_1，x_1) \ne-\psi (x_1，x_1) $，除非 $ \psi (x_1，x_1) = $0。
因此，必須選擇初始狀態來遵守這個反對稱屬性，然後在同一時間永遠不會有兩個電子處於相同的狀態。
這對電子結構而言很重要，因為它會禁止多個電子處於相同狀態，進而讓量子電腦使用單一量子位來將電子數目儲存在指定的量子狀態中。

雖然您可以藉由離散化這些狀態來模擬量子電腦上的量子機制，但是該欄位中的大部分工作都 eschewed 這種方法，因為它需要許多量子位來儲存狀態，而且需要複雜的狀態準備程式以準備反對稱的初始狀態。
幸運的是，這些問題可以藉由從不同的觀點來觀賞模擬問題來 sidestepped。
