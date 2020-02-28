---
title: 量子運算中的 qubit
description: 深入瞭解 qubits，這是量子運算的基本資訊單位。
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 770b739d95f5c1512234f6f7d2ca4544f1d80e64
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907523"
---
# <a name="the-qubit"></a>Qubit

就像是傳統運算中的基本資訊物件， [*qubits*](https://en.wikipedia.org/wiki/Qubit) （配量位）是量子運算中資訊的基本物件。  若要瞭解這種對應，讓我們來看一下最簡單的範例：單一 qubit。

## <a name="representing-a-qubit"></a>代表 Qubit

雖然位或二進位數位可以有 $0 $ 或 $1 $ 的值，但 qubit 可以有一個值，也就是其中一個或重迭為 $0 $ 和 $1 $ 的量子。

單一 qubit 的狀態可以由單元標準的二維資料行向量描述，也就是說，其專案的大小平方必須加總為 $1 $。 這個向量（稱為「配量狀態向量」）會保存描述一個 qubit 的量子系統所需的所有資訊，就像單一位一樣，可以保存描述二進位變數狀態所需的所有資訊。

具有標準 $1 $ 之實數或複數的任何二維資料行向量，代表 qubit 所持有的可能量子狀態。 因此，$ \begin{bmatrix} \Alpha \\\\ \Beta \end{bmatrix} $ 代表 qubit 狀態，如果 $ \Alpha $ 和 $ \Beta $ 是滿足 $ | \Alpha | ^ 2 + | \Beta | ^ 2 = $1 的複雜數位。 代表 qubits 的有效量子狀態向量範例包括

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}、\begin{bmatrix} 0 \\\\ 1 \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{1}{\sqrt{2}} \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{-1}{\sqrt{2}} \end{bmatrix}、\text{和} \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\ \frac{i}{\sqrt{2}} \end{bmatrix}. $ $

量子狀態向量 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ 和 $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ 接受特殊角色。 這兩個向量會形成向量空間的基礎，以描述 qubit 的狀態。 這表示任何量子狀態向量都可以撰寫為這些基礎向量的總和。 具體而言，向量 $ \begin{bmatrix} x \\\\ y \end{bmatrix} $ 可以撰寫為 $x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $。 雖然這些向量的任何旋轉都可做為 qubit 的有效基礎，但我們選擇以*計算為基礎*來進行這項工作的許可權。

我們會採用這兩個配量狀態來對應到傳統位的兩個狀態，即 $0 $ 和 $1 $。 標準慣例是選擇

$ $ 0 \ HTTP-equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}，\qquad 1 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}，$ $

雖然相反的選擇也同樣可行。 因此，不限數量的單一 qubit 量子狀態向量，只有兩個對應到傳統位的狀態;所有其他的配量狀態則否。

## <a name="measuring-a-qubit"></a>測量 Qubit

既然我們已經知道如何呈現 qubit，我們可以藉由討論[*測量*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)概念來取得這些狀態所代表的部分直覺。 量測會對應至 qubit 上「尋找」的非正式概念，這會立即折迭量子狀態為兩個傳統狀態 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ 或 $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $。 當配量狀態向量 $ \begin{bmatrix} \Alpha \\\\ \Beta \end{bmatrix} $ 所指定的 qubit 時，我們會取得結果 $0 $，機率為 $ | \Alpha | ^ 2 $ 和結果 $1 $ （機率為 $ | \Beta | ^ 2 $）。 在結果 $0 $ 中，qubit 的新狀態是 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $;結果 $1 $ 其狀態為 $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $。 請注意，由於正規化條件 $ | \Alpha | ^ 2 + | \Beta | ^ 2 = $1，這些機率會加總為 $1 $。

測量的屬性也表示量子狀態向量的整體正負號無關。 否定向量相當於 $ \Alpha \rightarrow-\Alpha $ 和 $ \Beta \rightarrow-\Beta $。 因為測量 $0 $ 和 $1 $ 的機率取決於詞彙的大小平方，所以插入這類符號並不會改變機率。 這類階段通常稱為[``*全域階段*' '](https://en.wikipedia.org/wiki/Phase_factor) ，而更一般的形式可以是 $e ^ {i \phi} $，而不只是 $ \pm $1。

測量的最後一個重要屬性是，它不一定會損毀所有的量子狀態向量。 如果我們從 state $ \begin{bmatrix} 1 的 qubit 開始 \\\\ 0 \end{bmatrix} $ （對應于傳統狀態 $0 $），測量此狀態一律會產生結果 $0 $，並讓配量狀態維持不變。 就這一點而言，如果我們只有傳統位（也就是 $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix} $ 或 $ \begin{bmatrix}0 \\\\ 1 \end{bmatrix} $），那麼測量就不會損毀系統。 這表示我們可以在量子電腦上複寫傳統資料，並將它操作，就像在傳統電腦上一樣。 不過，若要一次儲存這兩個狀態的資訊，您可以將配量運算提升至傳統方式，並進一步 robs 量子電腦不加上複製量子資料的能力，另請參閱[不復制定理](https://en.wikipedia.org/wiki/No-cloning_theorem)。

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>使用 Bloch 球體視覺化 Qubits 和轉換

Qubits 也可以使用[*Bloch 球體*](https://en.wikipedia.org/wiki/Bloch_sphere)標記法，以 $ 3 $ D 的形式呈現。  Bloch 球體提供一種方式來描述單一 qubit 的量子狀態（這是二維複雜向量），做為三維實值向量。  這點很重要，因為它可讓我們將單一 qubit 狀態視覺化，並藉此開發可在瞭解多 qubit 狀態時很有價值的理由（其中可惜 Bloch 球體標記法會細分）。  Bloch 球體可以視覺化如下：

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Bloch 球體](~/media/concepts_bloch.png)

此圖中的箭號顯示配量狀態向量的方向，而每個箭號的轉換都可以視為其中一個基線軸的旋轉。
雖然將量子計算視為一系列旋轉是一個強大的直覺，但是使用此直覺來設計和描述演算法是很困難的。 問 # 藉由提供描述這種旋轉的語言，來減輕這個問題。

## <a name="single-qubit-operations"></a>單一 Qubit 作業

量子電腦會套用一組通用的配量閘道來處理資料，以模擬配量狀態向量的任何旋轉。
這種 universality 概念與傳統（也就是傳統）運算的 universality 概念類似，如果輸入位的每個轉換都可以使用有限長度的線路來執行，則會將閘道集視為通用。
在量子運算中，我們允許在 qubit 上執行的有效轉換是單一轉換和測量。
Adjoint 作業或複雜的共軛轉型對量子*運算*而言相當重要，因為它是用來反轉量子轉換的必要項。
問 # 藉由提供可自動將閘道序列編譯到其 adjoint 的方法來反映這一點，這可讓程式設計人員在許多情況下都不需要撰寫程式碼 adjoints。 範例如下所示：

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

雖然這是一個簡單的範例（因為 <xref:microsoft.quantum.intrinsic.h> 作業是自我 adjoint），您可以看到這對更複雜的 qubit 作業變得很有用。
如需詳細資訊，請參閱[作業和函數](xref:microsoft.quantum.techniques.opsandfunctions)。

只有四個函式會將一個位對應到傳統電腦上的一個位。 相反地，在量子電腦上的單一 qubit 上有無限數量的單一轉換。 因此，沒有一組有限的基本量子作業，稱為網[*關*](https://en.wikipedia.org/wiki/Quantum_logic_gate)，可以完全複寫量子運算中所允許的一組無限單一轉換。 這表示與傳統運算不同的是，配量電腦無法完全使用有限數目的閘道來執行每個可能的量副程式。 因此，量子電腦不能在傳統電腦的相同意義上通用。 如此一來，當我們說出一組閘道是*通用*來進行配量運算時，我們實際上表示比傳統運算稍微弱一點。
針對 universality，我們需要配量電腦只在使用有限長度閘道序列的有限錯誤中，對每個單一矩陣進行*近似值*。
換句話說，如果有任何單一轉換可以從這個集合中的閘道乘積來撰寫，則一組閘道就是通用閘道集。 針對任何指定的錯誤系結，我們需要有閘道 $G _{1}，G_{2}，\ldots，G_N $ 來自閘道集，

$ $ G_N G_ {N-1} \cdots G_2 G_1 \approx U. $ $

請注意，由於矩陣乘法的慣例是在此順序中的第一個閘道運算的正向右乘以，$G _N $，實際上是最後一個套用至量子狀態向量的作業。 更正式的說，我們假設對於每個容錯 $ \epsilon > 0 $ 有 $G _1、\ldots、G_N $，因此 $G _N \ldots G_1 $ 和 $U $ 之間的距離最多為 $ \epsilon $。 理想的情況下，要達到 $ \epsilon $ 的這個距離所需的 $N $ 值應該使用 $ 1/\ epsilon $ 來調整 poly-logarithmically。

這種通用閘道集在實務上看起來是什麼樣子？  針對單一 qubit 閘道所設定的最簡單通用閘道是由兩個閘道所組成： Hadamard 閘道 $H $ 和所謂的 $T $-閘道（也稱為 $ \ pi/8 $ 閘道）：

$ $ H = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 &-1 \end{bmatrix}，\qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ {i \ pi/4} \end{bmatrix}。
$$

不過，基於與量子錯誤更正相關的實際原因，考慮較大的閘道集（也就是可以使用 $H $ 和 $T $ 來產生的）可能會更方便。
我們可以將配量管制分類為兩個類別： Clifford 閘道和 $T $-閘道。
這項劃分很有用，因為在許多量子錯誤更正配置中，所謂的 Clifford 閘道很容易實行，也就是說，它們在作業和 qubits 方面只需要很少的資源來執行錯誤 tolerantly，而非 Clifford 的閘道則是需要容錯時成本相當高。 [預設包含在 Q # 中](xref:microsoft.quantum.libraries.standard.prelude)的一組標準單一 qubit Clifford 閘道，包括

$ $ H = \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 &-1 \end{bmatrix}，\qquad S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix} = T ^ 2，\qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4 小時，$ $

$ $ Y = \begin{bmatrix} 0 &-i \\\\ & 0 \end{bmatrix} = T ^ 2HT ^ 4 HT ^ 6，\qquad Z = \begin{bmatrix}1 & 0\\\\ 0 &-1 \end{bmatrix} = T ^ 4。
$$

這裡的作業 $X $、$Y $ 和 $Z $ 特別常使用，而且在其 creator Wolfgang Pauli 之後，會命名為[*Pauli operators*](https://en.wikipedia.org/wiki/Pauli_matrices) 。
與非 Clifford 閘道（$T $-閘道）搭配使用時，可以撰寫這些作業來估計單一 qubit 上的任何單一轉換。

如需這些作業的詳細資訊、其 Bloch 球體標記法和 Q # 實作為，請參閱[內部作業和函數](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions)。

如需如何從這些基本專案建立單一轉換的範例，上述 Bloch 球體中所示的三個轉換對應至閘道序列 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $。

雖然先前的構成最受歡迎的基本閘道，可在堆疊的邏輯層級上描述作業（將邏輯層級視為配量演算法的層級），但是在演算法上考慮較少的基本作業通常會很方便層級，例如較接近函數描述層級的作業。 幸好，問 # 也有可用來執行較高層級 unitaries 的方法，而這可讓您在不明確分解所有專案到 Clifford 和 $T $-閘道的情況下，執行高階演算法。

最簡單的這種基本類型就是單一的 qubit 旋轉。 通常會考慮三個單一 qubit 旋轉： $R _x $、$R _y $ 和 $R _z $。 例如，若要以視覺化方式呈現旋轉 $R _x （\theta） $ 的動作，請想像以 Bloch 球體的 $x $ 軸方向指向右邊，並透過 $ \ theta/2 $ 弧度的角度旋轉向量。 這項令人困惑的 $2 $ 因素，是因為當繪製在 Bloch 球體上時，直角的向量是 $ 180 ^ \circ $，但實際上是 $ 90 ^ \circ $ 度數。 對應的單一矩陣如下：

\begin{align *} & R_z （\theta） = e ^ {-I\theta z/2} = \begin{bmatrix} e ^ {-i \ theta/2} & 0\\\\ 0 & e ^ {i \ theta/2} \end{bmatrix}，\\\\ & R_x （\theta） = e ^ {-I\theta x/2} = HR_z （\theta） H = \begin{bmatrix} \cos （\ theta/2） &-i\sin （\ theta/2）\\\\-i\sin （\ theta/2） & \cos （\ theta/2） \end{bmatrix}，\\\\ & R_y （\theta） = e ^ {-I\theta y/2} = SHR_z （\theta） HS ^ \dagger = \begin{bmatrix} \cos （\ theta/2） &-\sin （\ theta/2）\\\\ \sin （\ theta/2） & \cos （\ theta/2） \end{bmatrix}。\end{align*}

就像任何三個旋轉可以合併在一起，以在三個維度中執行任意旋轉，可以從 Bloch 球體標記法看出，任何單一矩陣也可以撰寫成三種旋轉的序列。 具體而言，針對每個單一矩陣 $U $ 存在 $ \Alpha、\Beta、\gamma、\delta $，$U = e ^ {i\Alpha} R_x （\Beta） R_z （\gamma） R_x （\delta） $。 因此 $R _z （\theta） $ 和 $H $ 也會構成通用閘道集，雖然 $ \theta $ 可以接受任何值。 基於這個理由，以及由於配量模擬中的應用程式，這類連續閘道對於量子計算很重要，尤其是在量子演算法設計層級。 為了達到容錯硬體的執行，最終會將它們編譯成緊密接近這些旋轉的離散閘道序列。
