---
title: Dirac 標記
description: 瞭解如何使用 Dirac 標記法來表示配量狀態和模擬量子作業。
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 204e56cc97fe28f9c52dcfb882aadec7e09bb2dc
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907557"
---
# <a name="dirac-notation"></a>Dirac 標記法

雖然資料行向量標記法線上性代數中是普遍的，但在處理多個 qubits 時，通常會難以進行量子計算。  例如，當我們將 $ \psi $ 定義為向量時，不會明確地清除 $ \psi $ 是否為數據列或資料行向量。  因此，如果 $ \phi $ 和 $ \psi $ 是向量，則即使已定義 $ \phi \psi $，也同樣不清楚，因為在內容中，$ \phi $ 和 $ \psi $ 的圖形可能不清楚。  除了向量形狀的多義性外，使用稍早引進的線性代數標記法來表示偶數的簡單向量也非常繁瑣。 例如，如果我們想要描述每個 qubit 都採用值 $0 $ 的 $n $ qubit 狀態，我們會正式地將狀態表示為 

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix}。 $$  

當然，評估此張量產品並不實用，因為向量位於指數大的空間，因此此標記法實際上是可使用先前的標記法提供之狀態的最佳描述。  

[*Dirac 標記法*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation)會藉由呈現新的語言，以符合精確的量子機制需求，來解決這些問題。  基於這個理由，我們建議讀者不要查看本節中的範例，做為如何描述配量狀態的一項嚴謹的處方，而是鼓勵讀者將這些內容視為可用於簡化量子概念的建議。

Dirac 標記法中有兩種類型的向量： *bra*向量和*ket*向量，因此名為，因為當放在一起時，它們會形成*braket*或內部產品。  如果 $ \psi $ 是資料行向量，則我們可以將它以 Dirac 標記法撰寫成 $ \ket{\psi} $，其中 $ \ket{\cdot} $ 代表它是單位資料行向量，亦即*ket*向量。  同樣地，資料列向量 $ \psi ^ \dagger $ 也會表示為 $ \bra{\psi} $。 換句話說，$ \psi ^ \dagger $ 的取得方式，是將進入的複雜 conjugation 套用至 $ \psi $ 的調換元素。 Bra-ket 標記法直接表示 $ \braket{\psi | \psi} $ 是向量 $ \psi $ 本身的內部乘積，其本身為 $1 $。  

更常見的情況是，如果 $ \psi $ 和 $ \phi $ 是配量狀態向量，則其內部產品是 $ \braket{\phi | \psi} $，表示測量 state $ \ket{\psi} $ 為 $ \ket{\phi} $ 的機率是 $ | \braket{\phi | \psi} | ^ 2 $。  

下列慣例是用來描述將零值和一個（單一 qubit 計算基礎狀態）編碼的量子狀態：

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0}、\qquad \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \ket{1}。
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>範例：代表具有 Dirac 標記法的 Hadamard 作業

下列標記法通常用來描述將 Hadamard 閘道套用至 $ \ket{0}$ 和 $ \ket{1}$ （對應至 Bloch 球體上 $ + x $ 和 $-x $ 指示中的單位向量）所產生的狀態：

$ $ \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H\ket{0} = \ket{+}，\qquad \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\-1 \end{bmatrix} = H\ket{1} = \ket{-}。
$$

您也可以使用 Dirac 標記法，將這些狀態擴充為 $ \ket{0}$ 和 $ \ket{1}$ 的總和：

$ $ \ket{+} = \frac{1}{\sqrt{2}} （\ket{0} + \ket{1}），\qquad \ket{-} = \frac{1}{\sqrt{2}} （\ket{0}-\ket{1}）。
$$

### <a name="computational-basis-vectors"></a>計算基礎向量
這會示範為什麼這些狀態通常稱為「*計算基礎*」：每個配量狀態一律會以計算基礎向量的總和表示，而這類總和則可以使用 Dirac 標記法輕鬆表示。  相反的情況也是如此，狀態 $ \ket{+} $ 和 $ \ket{-}$ 也會構成量子狀態的基礎。  您可以從下列事實看出

$ $ \ket{0} = \frac{1}{\sqrt{2}} （\ket{+} + \ket{-}），\qquad \ket{1} = \frac{1}{\sqrt{2}} （\ket{+}-\ket{-}）。
$$

做為 Dirac 標記法的範例，請考慮 braket $ \braket{0 | 1} $，這是介於 $0 $ 和 $1 $ 之間的內部產品。  它可以撰寫成 

$ $ \braket{0 | 1} = \begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1 \ end {bmatrix} = 0. $ $

這表示 $ \ket{0}$ 和 $ \ket{1}$ 是正則向量，這表示 $ \braket{0 | 1} = \braket{1 | 0} = $0。  此外，定義 $ \braket{0 | 0} = \braket{1 | 1} = 1 $，這表示兩個計算基礎向量也可以稱為*orthonormal*。
這些 orthonormal 屬性在下列範例中將會很有用。 如果我們有 state $ \ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$，因為 $ \braket{1 | 0} = $0，測量 $1 $ 的機率是  

$ $ \big | \braket{1 | \psi}\big | ^ 2 = \left | \frac{3}{5}\braket{1 | 1} + \frac{4}{5}\braket{1 | 0} \right | ^ 2 = \frac{9}{25}. $ $ 

### <a name="tensor-product-notation"></a>張量產品標記法
Dirac 標記法也會在其中包含隱含的張量產品結構。  這一點很重要，因為在量子運算中，兩個不相關的量子暫存器所描述的狀態向量是兩個狀態向量的張量產品。  如果您想要說明配量計算，就很重要的是，描述張量產品結構或缺乏的架構。  張量產品結構意指，我們可以撰寫 $ \psi \otimes \phi $ for any 量子 state 向量 $ \phi $ 和 $ \psi $ as $ \ket{\psi} \ket{\phi} $，有時會以 $ \ket{\psi} \otimes \ket{\phi} $ 的方式明確寫入，但會依照慣例寫入 $ \otimes $不需要在向量之間進行。  例如，具有兩個 qubits 初始化為零狀態的狀態會由指定

$ $ \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}。
$$

同樣地，integer $p $ 的 state $ \ket{p} $ 代表以 binary 標記法編碼的量子狀態，其整數 $p $。  例如，如果我們想要使用不帶正負號的二進位編碼來表示數位 $5 $，我們可以同樣地將其表示為

$ $ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}。
$$

在此標記法中，$ \ket{0}$ 不需要參考單一 qubit 狀態，而是*qubit*暫存器儲存 $0 $ 的二進位編碼。  這兩種標記法之間的差異通常會從內容中清楚明瞭。  此慣例適用于簡化第一個範例，可以透過下列任何方式撰寫：

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= | 0 \ cdots 0 \ rangle = \ket{0}^ {\otimes n} = \ket{0}。
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>範例：描述具有 Dirac 標記法的重迭
如需如何使用 Dirac 標記法來描述配量狀態的另一個範例，請考慮下列寫入配量狀態的相同方式，這在每個可能的長度字串中都是相等的重迭 $n $

$ $ H ^ {\otimes n} \ket{0} = \frac{1}{2 ^ {n/2}} \ sum_ {j = 0} ^ {2 ^ n-1} \ket{j} = \ket{+} ^ {\otimes n}。
$$

在這裡，您可能會想知道總和為何會從 $0 $ 到 $ 2 ^ {n}-$1 （$n $ bits）。  首先要注意的是，有 $ 2 ^ {n} $ 個不同的設定，$n $ bits 可以採用。  您可以看到，其中一個位可以接受 $2 $ 值，但兩個位可以接受 $4 $ 值等等。 一般來說，這表示有 $ 2 ^ n $ 個不同的可能位字串，但以任何 $ 1 \ cdots 1 = 2 ^ n-$1 編碼的最大值，因此是總和的上限。
請注意，在此範例中，我們並未使用 $ \ket{+} ^ {\otimes n} = \ket{+} $ 來類比 $ \ket{0}^ {\otimes n} = \ket{0}$，因為此標記慣例通常會保留給每個 qubit 初始化為零的計算基礎狀態。  雖然這種慣例在此情況下很合理，但不會在「量子計算」文獻中採用。

### <a name="expressing-linearity-with-dirac-notation"></a>使用 Dirac 標記法來表示線性
Dirac 標記法還有另一項不錯的功能，就是它是線性的事實。  如果我們想要撰寫四個量子狀態向量， 

$ $ （\Alpha \ket{\psi} + \Beta\ket{\phi}） \otimes （\gamma \ket{\chi} + \delta \ket{\omega}） = \Alpha\gamma \ket{\psi}\ket{\chi} + \Alpha\delta \ket{\psi}\ket{\omega} + \Beta\gamma\ket{\phi}\ket{\chi} + \Beta\delta\ket{\phi}\ket{\omega}. $ $

也就是說，您可以在 Dirac 標記法中散發張量產品標記法，讓州向量之間的張量產品看起來就像一般乘法。

Bra 向量遵循類似的慣例來 ket 向量。  例如，vector $ \bra{\psi}\bra{\phi} $ 相當於狀態向量 $ \psi ^ \dagger \otimes \phi ^ \dagger = （\psi\otimes \phi） ^ \dagger $。 如果 ket vector $ \ket{\psi} $ 是 $ \Alpha \ket{0} + \Beta \ket{1}$，則向量的 bra 向量版本是 $ \bra{\psi} = \ket{\psi} ^ \dagger = （\bra{0}\Alpha ^ * + \bra{1}\Beta ^ *） $。

例如，假設我們想要計算測量 state $ \ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ 的機率，方法是使用配量程式將狀態測量為 $ \ket{+} $ 或 $ \ket{-}$。 然後，裝置會輸出狀態為 $ \ket{-}$ 的機率為 

$ $ | \braket{-| \psi} | ^ 2 = \left | \frac{1}{\sqrt{2}} （\bra{0}-\bra{1}）（\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}） \right | ^ 2 = \left |-\frac{3}{5 \ sqrt{2}} + \frac{4}{5 \ sqrt{2}} \right | ^ 2 = \frac{1}{50}

負號出現在機率計算中的事實，是一種量子干擾的表現，這是配量運算透過傳統運算獲得優勢的機制之一。

## <a name="ketbra-or-outer-product"></a>ketbra 或外部產品
在 Dirac 標記法中，值得討論的最後一個專案是*ketbra*或外部產品。  外部產品在 Dirac 標記法中是以 $ \ket{\psi} \bra{\phi} $ 的形式呈現，有時也稱為 ketbras，因為 bras 和 kets 的順序會與 brakets 相反。  外部產品是透過矩陣乘法定義為 $ \ket{\psi} \bra{\phi} = \psi \phi ^ \dagger $ （適用于量子狀態向量 $ \psi $ 和 $ \phi $）。  最簡單且可說是此標記法的最常見範例，就是

$ $ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1 & 0 \end{bmatrix} = \begin{bmatrix}1 & 0\\\\ 0 & 0 \ 結束 {bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0 & 1 \end{bmatrix} = \begin{bmatrix}0 & 0\\\\ 0 & 1 \ end {bmatrix}。
$$

Ketbras 通常稱為投影機，因為它們會將配量狀態投射到固定值上。  因為這些作業不是單一的（而且甚至不會保留向量的標準），所以量子電腦無法以決定性的方式套用投影機，應該不會感到驚訝。  不過，投影機會執行一項美觀的作業來描述測量在配量狀態上的動作。  例如，如果我們將 state $ \ket{\psi} $ 測量為 $0 $，則產生的轉換會因為測量而導致狀態體驗

  $ $ \ket{\psi} \rightarrow \frac{（\ket{0} \bra{0}） \ket{\psi}}{| \braket{0 | \psi} |}= \ket{0}，$ $

如果您要測量狀態，並將其視為 $ \ket{0}$，則會預期為一。  再次重申，這類投影機無法以決定性的方式套用到量子電腦上的狀態。  相反地，它們可以使用結果 $ \ket{0}$ 來隨機套用，並顯示一些固定機率。  這類測量的機率可能會以狀態中的「量子投影機」預期值來寫入

$ $ \bra{\psi} （\ket{0} \bra{0}） \ket{\psi} = | \braket{\psi | 0} | ^ 2，$ $

其中說明投影機只是提供一種新的方式來表達測量流程。

如果改為考慮將多 qubit 狀態的第一個 qubit 測量為 $1 $，我們也可以使用投影機和 Dirac 標記法來方便地描述此程式：

$ $ P （\text{first qubit = 1}） = \bra{\psi}\left （\ket{1}\bra{1}\otimes \boldone ^ {\otimes n-1} \right） \ket{\psi}。
$$

在這裡，您可以用 Dirac 標記法輕鬆地將身分識別矩陣寫成

$ $ \boldone = \ket{0} \bra{0}+ \ket{1} \bra{1}= \begin{bmatrix}1 & 0\\\\ 0 & 1 \end{bmatrix}。
$$

在有兩個 qubits 的情況下，投影機可以擴充為 

$ $ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes （\ket{0} \bra{0}+ \ket{1} \bra{1}） = \ket{10}\bra{10} + \ket{11}\bra{11}。
$$

然後，我們可以看到這與使用資料行向量標記法之 multiqubit 狀態的度量 likelihoods 討論一致：

$ $ P （\text{first qubit = 1}） = \psi ^ \dagger （e\_{10}e\_{10}^ \dagger + e\_{11}e\_{11}^ \dagger） \psi = | e\_{10}^ \dagger \psi | ^ 2 + | e\_{11}^ \dagger \psi | ^ 2，$ $

其中符合多 qubit 的測量討論。  不過，此結果對多 qubit 案例的一般化，使用 Dirac 標記法比資料行向量標記法更直接表達，而且完全等同于先前的處理。

## <a name="density-operators"></a>密度運算子

另一個使用 Dirac 標記法來表示的有用運算子是*密度運算子*，有時也稱為「*狀態運算子*」。
量子狀態向量的密度運算子採用 $ \rho = \ket{\psi} \bra{\psi} $ 的格式。
將狀態表示為矩陣（而不是向量）的這個概念通常很方便，因為它提供便利的方式來表示機率計算，也允許一個描述統計不確定性以及量子不確定性。在同一個形式中。
一般的量子狀態運算子（而不是向量）在量子運算的某些區域中很普遍，但不一定要瞭解此欄位的基本概念。
對於感興趣的讀者，建議您閱讀中所提供的其中一個參考書籍，[以取得詳細資訊](xref:microsoft.quantum.more-information)。

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Q # 閘道序列相當於量子狀態
關於量子標記法和 Q # 程式設計語言的最後一點：我們在本檔的萌芽中提到，配量狀態是量子運算中資訊的基本物件。  這可能會令人驚訝的是，在問 # 中，沒有配量狀態的概念。  相反地，所有狀態只會由用來準備它們的作業來描述。  先前的範例是這個的絕佳說明。  我們可以將結果表示為 $H ^ {\otimes n} \ket{0}$，而不是在暫存器中的每個配量位字串上表示統一重迭。  這種狀態的指數較短描述不僅具有我們可以傳統方式其相關原因的優點，還會簡明扼要地定義透過軟體堆疊傳播以執行演算法所需的作業。  基於這個理由，Q # 的設計是用來發出閘道序列，而不是配量狀態。不過，理論層級的兩個觀點是相等的。
