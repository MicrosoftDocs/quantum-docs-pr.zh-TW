---
標題：量子位的量子運算描述：瞭解量子位，這是量子運算中的基本資訊單位。
作者： QuantumWriter uid：量子位 ms. 作者： v-benbra ms. date： 12/11/2017 ms. 主題：概念無 loc：
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---
# <a name="the-qubit"></a>量子位

就像位是傳統運算中資訊的基礎物件一樣， [*量子位*](https://en.wikipedia.org/wiki/Qubit) (量子 bits) 是量子運算中資訊的基礎物件。  若要瞭解這種對應，讓我們看看最簡單的範例：單一量子位。

## <a name="representing-a-qubit"></a>代表量子位

雖然位或二進位位數可以有 $ 0 $ 或1的值，但 $ $ 量子位可以有一個值，也就是 $ 0 和1的量子迭加 $ $ $ 。

單一量子位的狀態可由單元度量的二維資料行向量描述，也就是其專案的大小平方必須加總為 $ 1 $ 。 這個稱為量子狀態向量的向量會保存描述單一量子位量子系統所需的所有資訊，就像單一位一樣，它會保留描述二進位變數狀態所需的所有資訊。

具有標準1之實數或複數的任何二維資料行向量，都 $ $ 代表量子位所持有的可能量子狀態。 因此 $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ $ \alpha $ ，如果和 $ \beta $ 是滿足 $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ 的複數，則表示量子位狀態。   代表量子位的有效量子狀態向量的一些範例包括

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} 、 \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { 1 } { \sqrt { 2 } } \end{bmatrix} 、 \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { -1 } { \sqrt { 2 } } \end{bmatrix} \text { 和 } \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { i } { \sqrt { 2 } } \end{bmatrix} 。      $$

量子狀態向量 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ 和 $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ 採用特殊角色。 這兩個向量會形成描述量子位狀態的向量空間基礎。 這表示任何量子狀態向量都可以撰寫為這些基礎向量的總和。 具體而言，向量 $ \begin{bmatrix} x \\\\ y \end{bmatrix} $ 可以撰寫為 $ x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ 。 雖然這些向量的任何旋轉都可做為量子位的完全有效基礎，我們也選擇以 *計算為基礎* 來為其提供許可權。

我們會將這兩個量子狀態對應至傳統位（亦即 $ 0 和1）的兩個狀態 $ $ $ 。 標準慣例是選擇

$$0 \equiv \begin{bmatrix} 1 \\\\  0 \end{bmatrix} 、 \qquad 1 \equiv \begin{bmatrix} 0 \\\\  1 \end{bmatrix} 、$$

雖然相反的選擇也可以被採用。 因此，不限數目的可能單一量子位量子狀態向量，只有兩個對應至傳統位的狀態;其他所有的量子狀態則否。

## <a name="measuring-a-qubit"></a>測量量子位

現在我們已經知道如何呈現量子位，我們可以討論 [*測量*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)的概念，以取得這些狀態所代表的部分直覺。 測量結果對應于在量子位上「查看」的非正式構想，這會立即將量子狀態折迭為兩個傳統狀態 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ 或 $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ 的其中一個。 測量量子狀態向量所指定的量子位時 $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ ，我們會取得機率 $ 為 ^ 2 的結果0和機率為 $ $ | \alpha | $ $ $ $ | \beta | ^ 2 $ 的結果1。   在結果 $ 0 上 $ ，量子位的新狀態為 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ; 在結果 $ 1 上， $ 其狀態為 $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ 。 請注意， $ $ 由於正規化條件 $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ ，這些機率會加總為1。

度量的屬性也表示量子狀態向量的整體正負號是不相關的。 否定向量相當於箭號 $ \alpha \right \alpha $ 和箭號 $ \beta \right \beta $ 。 因為測量 $ 0 $ 和1的機率 $ $ 取決於詞彙的範圍平方，所以插入這類正負號並不會改變機率。 這類階段通常稱為「 [ `` *全域階段」（global 階段*' '](https://en.wikipedia.org/wiki/Phase_factor) ），更一般的形式可以是 $ e ^ { i， \phi } $ 而不只是 $ \pm 1 $ 。

測量的最後一個重要屬性是它不一定會損毀所有的量子狀態向量。 如果我們從狀態 1 0 的量子位開始 $ \begin{bmatrix} \\\\ \end{bmatrix} $ （對應至傳統狀態 $ 0） $ ，測量此狀態一律會產生結果 $ 0， $ 並讓量子狀態保持不變。 在這種情況下，如果我們只有傳統的位 (也就是量子位，也就是 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ 或 $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $) 然後測量則不會損毀系統。 這表示我們可以在量子電腦上複寫傳統資料並操作，就像在傳統電腦上一樣。 不過，若要一次將資訊儲存在這兩個狀態中，就能將量子運算提升至可能的傳統方式，並進一步 robs 量子電腦不限複製量子資料的能力，另請參閱 [無複製定理](https://en.wikipedia.org/wiki/No-cloning_theorem)。

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>使用布洛赫球體視覺化量子位和轉換

量子位也可以 $ $ 使用 [*布洛赫球體*](https://en.wikipedia.org/wiki/Bloch_sphere) 標記法，以 3 D 表示。  布洛赫球體提供一種方式來描述單一量子位的量子狀態 (這是一種二維的複雜向量，) 為三維實值向量。  這點很重要，因為它可讓我們將單一量子位狀態視覺化，並藉此開發有助於瞭解多重量子位狀態的原因， (在可惜布洛赫球體標記法會細分) 。  布洛赫球體可哥視化如下：

<!--- ![](.\media\bloch.svg) { 寬度 = 50%} --->
![布洛赫球體](~/media/concepts_bloch.png)

此圖表中的箭號會顯示配量狀態向量的方向，而每個箭號的轉換都可視為圍繞其中一個基線軸的旋轉。
雖然將量子計算視為一連串的旋轉是一個強大的直覺，但使用此直覺來設計和描述演算法是很困難的。 Q# 藉由提供描述這類旋轉的語言來緩和此問題。

## <a name="single-qubit-operations"></a>Single-Qubit 作業

量子電腦藉由套用一組通用的量子閘道來處理資料，以模擬量子狀態向量的任何旋轉。
這種 universality 概念與傳統 (的概念類似 universality 的概念，例如，如果輸入位的每個轉換都可以使用有限的長度電路來執行，則會將閘道組視為通用的傳統) 計算。
在量子運算中，我們允許在量子位上執行的有效轉換是單一轉換和測量。
Adjoint 作業或複雜的共軛轉型對於量子 *運算* 而言相當重要，因為它是將量子轉換進行反轉的必要動作。

傳統電腦上只有四個函式會將一個位對應到一個位。 相反地，在量子電腦上的單一量子位上有無限的單一轉換。 因此，沒有一組有限的基本量子作業（稱為網 [*關*](https://en.wikipedia.org/wiki/Quantum_logic_gate)）可以完全複寫量子運算中所允許的一組無限單一轉換。 這表示與傳統運算不同的是，量子電腦無法完全使用有限數目的閘道來執行每個可能的量副程式。 因此，量子電腦不能以傳統電腦的相同方式進行通用。 如此一來，當我們說出一組適用于量子運算的網 *關時，* 實際上是指比傳統運算稍微差一點。
針對 universality，我們要求量子電腦只在使用有限長度閘道序列的有限錯誤中， *大約* 每個單一矩陣。
換句話說，如果任何單一轉換都可以從這個集合中以閘道作為基礎來撰寫，則一組閘道會設定為通用閘道。 針對任何指定的錯誤系結，我們需要有一個閘道 $ G_ { 1 } 、G_ { 2 } 、\ldots、G_N $ 來自閘道集合，

$$
G_N G_ { N-1 } \cdots G_2 G_1 \approx U。 $$

請注意，由於矩陣乘法的慣例是要從右至左乘以此序列中的第一個閘道運算， $ G_N $ 實際上是最後一個套用至量子狀態向量的作業。 更正式來說，如果每個容錯 $ \epsilon > 0 $ 存在 $ G_1、\ldots G_N，讓 $ $ G_N \ldots G_1 和 U 之間的距離 $ $ $ 最 $ \epsilon $ ，則我們假設這類閘道集是通用的。 在理想的情況下， $ $ 達到 \epsilon 距離所需的 N 值 $ 應該以 $ $ 1/\ epsilon 來調整 poly logarithmically $ 。

這類通用閘道在實務上的外觀為何？  單一量子位閘道的最簡單這類通用閘道是由兩個閘道所組成： Hadamard 閘道 $ H $ 和所謂的 T 閘道 $ $ (也稱為 $ \ pi/8 網 $ 關) ：

$$
H = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix} ， \qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ { i \ pi/4 } \end{bmatrix} 。
$$

不過，對於與量子錯誤更正相關的實際原因，最好考慮較大的閘道集，也就是可以使用 $ H $ 和 T 產生的 $ 設定 $ 。我們可以將量子閘道分類成兩種類別： Clifford 閘道和 $ T 網 $ 關。
這項細分會很有用，因為在許多量子錯誤修正配置中，所謂的 Clifford 閘道很容易執行，這就是在作業和量子位方面需要很少的資源來執行容錯 tolerantly，而非 Clifford 閘道在需要容錯時相當昂貴。 一組標準的單一量子位 Clifford 閘道，[預設包含在中 Q# ](xref:microsoft.quantum.libraries.standard.prelude)，包括

$$
H = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix} ， \qquad S = \begin{bmatrix} 1 & 0 \\\\ 0 0 & i \end{bmatrix} = T ^ 2， \qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4H，$$

$$
Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix} = T ^ 2HT ^ 4 HT ^ 6， \qquad Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} = T ^ 4。
$$

在這裡， $ 會 $ $ 特別使用 X、Y $ 和 Z 等作業 $ $ ，並在其建立者 Wolfgang Pauli 之後將其命名為 [*Pauli 操作員*](https://en.wikipedia.org/wiki/Pauli_matrices) 。
除了 (T 閘道) 的非 Clifford 閘道之外 $ $ ，這些作業也可以撰寫成近似單一量子位上的任何單一轉換。

如需這些作業的詳細資訊、其布洛赫球體標記法和實作為 Q# ，請參閱 [內部作業和](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions)函式。

如需如何從這些基本專案建立單一轉換的範例，上述布洛赫球體中所示的三個轉換對應至閘道序列 $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ 。

雖然前一個是在堆疊的邏輯層級上描述作業的最受歡迎基本閘道 (將邏輯層級視為量子演算法) 的層級，但在演算法層級考慮較少基本作業（例如更接近函式描述層級的作業）通常很方便。 幸運的是， Q# 也有方法可執行較高層級的 unitaries，進而讓高階演算法得以執行，而不需明確地分解到 Clifford 和 $ T $ 管制。

最簡單的這類基本功能是單一量子位旋轉。 通常會考慮三個單一量子位的旋轉： $ R_x $ 、 $ R_y $ 和 $ R_z $ 。 例如，若要將旋轉 R_x 的動作視覺化 $ ( \theta) $ ，請想像一下布洛赫球體 X 軸方向的右手邊 $ ， $ 並以 $ \ theta/2 弧度的角度旋轉向量 $ 。 這種混淆因數 $ 2 $ 的原因是，在 $ $ 繪製于布洛赫球體的情況下，正向向量的 \circ 相隔 180 ^，但實際上是沿著 $ 幾何的 90 ^ \circ $ 角度。 對應的單一矩陣如下：

\begin{align *} 
 & R_z ( \theta) = e ^ { -i\theta z/2 } = \begin{bmatrix} e ^ { -i \ theta/2 } & 0 \\\\ 0 & e ^ { i \ theta/2 } \end{bmatrix} ， \\\\ 
 & R_x ( \theta) = e ^ { -i\theta x/2 } = HR_z ( \theta) H = \begin{bmatrix} \cos ( \ theta/2) & -i\sin () \\\\ & i\sin ( \ theta/2) \end{bmatrix} \\\\ 
 & R_y ( \theta) = e ^ { -i\theta y/2 } = SHR_z ( \theta) HS ^ \dagger = \begin{bmatrix} \cos ( \ theta/2) & -\sin ( \ theta/2) \\\\ \sin ( \ theta/2) & \cos ( \ theta/2) \end{bmatrix} 。 \end {對齊*}

就像任何三個旋轉可以結合在一起以執行三個維度的任意旋轉，也可以從布洛赫球體標記法看出，任何單一矩陣也可以撰寫成三個旋轉的序列。 具體來說，每個單一矩陣 $ U 都 $ 有，， $ \alpha \beta \gamma \delta $ 因此 $ u = e ^ { i \alpha } R_x (\beta) R_z (\gamma \delta $) R_x () 。 因此 $ R_z ( \theta) $ 和 $ H $ 也會形成通用閘道集，但它並不是離散的閘道集，因為 $ \theta $ 可以採用任何值。 基於這個原因，以及由於量子模擬中的應用程式，這類連續閘道對於量子計算很重要，尤其是在量子演算法設計層級。 為了達成容錯硬體的執行，最終會將它們編譯成與這些旋轉相近的離散閘道序列。
