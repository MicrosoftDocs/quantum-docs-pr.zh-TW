---
title: 量子計算的線性代數
description: 了解要對量子運算有所認識所需要的基本線性代數概念
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
ms.openlocfilehash: 9f156a3cc092e295317061dda5e8aa29e9d5ca1e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430844"
---
# <a name="linear-algebra-for-quantum-computing"></a>量子計算的線性代數

線性代數是量子運算的語言。 雖然不了解線性代數也可以實作或撰寫量子程式，但線性代數卻廣泛用於描述量子位元狀態、量子運算，以及用於預測量子電腦為了回應一連串指示所會執行的動作。

熟悉[量子物理的基本概念](xref:microsoft.quantum.overview.understanding)可以協助您了解量子運算，同樣地，了解一些基本的線性代數也可以協助您了解量子演算法的運作方式。 至少請熟悉**向量**和**矩陣乘法**。 如果您需要複習這些代數概念知識，以下是一些涵蓋基本知識的教學課程：

- [關於線性代數的 Jupyter 筆記本教學課程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
- [關於複數運算的 Jupyter 筆記本教學課程](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
- [量子運算的線性代數](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [線性代數的基本概念](https://www.math.ubc.ca/~carrell/NB.pdf)
- [量子運算入門](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>量子運算中的向量和矩陣

在[了解量子運算](xref:microsoft.quantum.overview.understanding)的主題中，您曾看到量子位元的狀態可以是 1 或 0 或疊加或兩者。 使用線性代數時，量子位元的狀態可以用向量加以描述，並以單行**矩陣** $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 來呈現。 這也稱為**量子狀態向量**，而且必須符合 $|a|^2 + |b|^2 = 1$ 的要求。  

矩陣的元素代表量子位元塌縮向某一方的概率，其中 $|a|^2$ 是塌縮為 0 的概率，而 $|b|^2$ 則是塌縮為 1 的概率。 下列矩陣全都代表有效的量子狀態向量：

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}、\begin{bmatrix} 0 \\\\  1 \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}、\text{ 和 }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

在[量子電腦和量子模擬器](xref:microsoft.quantum.overview.simulators)中，您也曾看到量子運算可用來修改量子位元的狀態。  量子運算也可以透過矩陣來表示。 對量子位元套用了量子運算時，其各自的代表矩陣會相乘，產生的答案則代表量子位元在運算後的新狀態。  

以下是以矩陣乘法所呈現的兩個常見量子運算。


[`X` 運算](xref:microsoft.quantum.intrinsic.x)會以 Pauli 矩陣 $X$ 來表示，

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}，$$
    
並可用來將量子位元的狀態從 0 翻轉為 1 (反之亦然)，例如

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}。$$

['H' 運算](xref:microsoft.quantum.intrinsic.h)會以 Hadamard 變換 $H$ 來表示，

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}，$$

 並且會將量子位元進入疊加態，使其有均等的概率塌縮向任一方，如下所示

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}。$$

代表量子運算的矩陣有一個要求，那就是其必須是**麼正** (unitary) 矩陣。 如果某個矩陣的**逆**矩陣等於該矩陣的**共軛轉置**矩陣，該矩陣便是麼正矩陣。

## <a name="representing-two-qubit-states"></a>代表兩個量子位元狀態

在上述範例中，一個量子位元的狀態使用單行矩陣 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 來描述，而對其套用運算的行為則以乘上兩個矩陣來描述。 不過，量子電腦會使用多個量子位元，因此該如何描述兩個量子位元的結合狀態呢？ 

請記住，每個量子位元都是一個向量空間，因此不能直接相乘。 相反地，您必須使用**張量積**，這是一種相關運算，會從個別向量空間建立新的向量空間，並以 $\otimes $ 符號表示。 例如，兩個量子位元狀態 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 和 $\begin{bmatrix} c \\\\  d \end{bmatrix}$ 的張量積計算如下

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}。
$$

所得結果是一個四維矩陣，每個元素各自代表一個概率。 例如，$ac$ 是塌縮為 0 和 0 的兩個量子位元所具有的概率，$ad$ 則是 0 和 1 的概率，依此類推。 

單一量子位元狀態 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ 必須符合 $|a|^2 + |b|^2 = 1$ 的要求才能表示量子狀態，同樣地，雙量子位元的狀態 $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ 也必須符合 $|a|^2 + |b|^2 + |c|^2+ |d|^2 = 1$ 的要求。

## <a name="summary"></a>摘要

線性代數是用來描述量子運算和量子物理的標準語言。 雖然 Microsoft Quantum 開發套件隨附的[程式庫](xref:microsoft.quantum.libraries)可協助您不必深入了解基礎的數學運算就能執行進階的量子演算法，但了解基本概念可協助您快速入門，並提供扎實的建立基礎。

## <a name="next-steps"></a>後續步驟

> [!div class="nextstepaction"]
> [安裝 QDK](xref:microsoft.quantum.install)