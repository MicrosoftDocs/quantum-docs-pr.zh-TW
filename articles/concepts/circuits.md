---
標題：配量線路描述：瞭解如何以視覺化方式呈現使用配量線路圖表的簡單和複雜配量作業。
author： QuantumWriter uid： microsoft 量子.. m. m. a m. nawiebe@microsoft.com date： 12/11/2017 ms. 主題：不含 loc 的文章：
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

# <a name="quantum-circuits"></a>量子線路
請思考一下單一轉換 $ \text { cnot-contains } _ { 01 } (H \otimes 1) $ 。
此閘道序列對量子運算的基本重要性，因為它會建立最常光子二 qubit 的狀態：

$$\mathrm{Cnot-contains } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left (\ket { 00 }  +  \ket { 11 } \right) ，$$

具有此或更大複雜度的作業在配量演算法和量子錯誤更正中是普遍的，因此，它應該是一個簡單的視覺效果方法，稱為配量*線路圖*。
準備此最常光子量子狀態的線路圖表如下：

<!--- ![](.\media\1.svg) --->
<!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：-->
![最常光子二 qubit 狀態的電路圖](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>配量線路圖慣例
當您瞭解用來表示配量線路的慣例之後，可以更輕鬆地消化量子作業的視覺化語言，而不是寫下其對等的矩陣。
我們會在下面探討這些慣例。

在電路圖中，每一條實線描述一個 qubit 或更普遍的 qubit 暫存器。
依照慣例，第一行是 qubit 暫存器 $ 0 $ ，其餘部分則以順序標示。 上述的範例電路會在兩個 qubits (或等同兩個由一個 qubit) 組成的暫存器上，描述為作用。
以一個或多個 qubit 暫存器為作用的閘道會以方塊表示。
例如，符號

<!--- ![](.\media\2.svg) --->
<!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：-->
![Hadamard 作業的符號，適用于單一 qubit 暫存器](~/media/2.svg)

是在單一 qubit 暫存器上運作的[Hadamard](xref:microsoft.quantum.intrinsic.h)作業。

配量閘道會按照時間順序排列，並以最左邊的閘道作為第一次套用到 qubits 的閘道。
換句話說，如果您將線路畫成包含配量狀態，則電線會從左至右的圖表中的每個閘道顯示配量狀態。
也就是說 

<!--- ![](.\media\3.svg) --->
<!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：-->
![由左至右套用的量子閘道圖](~/media/3.svg)

是單一矩陣 $ CBA $ 。
矩陣乘法遵守相反的慣例：第一次套用最右邊的矩陣。 不過，在配量電路圖中，會先套用最左邊的閘道。
這項差異有時可能會造成混淆，因此請務必注意線性代數標記法與配量電路圖之間的顯著差異。

## <a name="inputs-and-outputs-of-quantum-circuits"></a>量子線路的輸入和輸出
所有先前的範例都具有精確的線路數， (qubits) 輸入到配量閘道，做為從量子閘道的線路數目。
一般來說，配量線路可能會有比一般輸入更多或更少的輸出。
不過，這是不可能的，因為所有的量子作業、儲存量測都是單一的，因此可以還原。
如果它們沒有與輸入相同的輸出數目，它們將無法復原，因此不是單一的，這是一項衝突。
基於這個理由，在電路圖中繪製的任何方塊都必須有相同數目的線路進入結束。

多 qubit 的電路圖表會遵循類似的慣例來進行單一 qubit。
做為說明範例，我們可以定義兩個 qubit 的單一作業 $ B $ $ (H S \otimes X) $ ，並以等同的方式表達線路

<!--- ![](.\media\4.svg) --->
<!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：-->
![兩個 qubit 的單一作業的路線圖](~/media/4.svg)

我們也可以根據 $ $ 使用線路的內容，在單一雙 qubit 暫存器（而不是 2 1-qubit 暫存器）上查看 B。 這類抽象循環圖表表可能是最有用的屬性，因為它們可讓複雜的量子演算法以高階方式描述，而不需要將它們編譯成基本閘道。
這表示您可以針對大型配量演算法取得資料流程的直覺，而不需要瞭解演算法中每個副程式如何工作的所有詳細資料。

## <a name="controlled-gates"></a>控制的閘道
另一個內建于多 qubit 配量電路圖的結構是 control。
配量單一控制閘道的動作（以 qubit g) 表示），您 $ \Lambda 可以藉 $ $ $ 由查看下列產品狀態 (輸入的範例，來瞭解如何 (0 $ \Lambda \alpha \ket { }  +  \beta \ket { 1 } \ket { \psi } = \alpha \ket { } \ket { \psi }  +  \beta \ket { } g \ket { \psi } $) 0 的) ，藉此識別出 g 的應用程式 (。也就是說， $ $ 只有在 $ \psi $ 控制項 qubit 接受值 $ 1 $ 時，受控制的閘道才會將 G 套用至包含 if 和的暫存器。
一般來說，我們會在電路圖中描述這類受控制的作業，如下所示：

<!--- ![](.\media\5.svg) --->
<!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：-->
![單向控制閘道的路線圖](~/media/5.svg)

在這裡，黑色圓圈代表控制閘道的配量位，而垂直線代表當控制項 qubit 接受值1時所套用的單一 $ $ 。
在 $ g X 和 g Z 的特殊案例中， = $ $ = $ 我們引進了下列標記法來描述控制的閘道版本 (請注意，控制的 X 閘道是[ $ cnot-contains 網 $ 關](xref:microsoft.quantum.intrinsic.cnot)) ：

<!--- ![](.\media\6.svg) --->
<!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：-->
![控制閘道特殊案例的電路圖](~/media/6.svg)

Q#提供自動產生受控制版本之作業的方法，可讓程式設計人員不必手動撰寫這些作業的程式碼。 範例如下所示：

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>測量運算子
要在電路圖中視覺化的其餘作業是測量。
測量會採用 qubit 暫存器、加以測量，然後將結果輸出為傳統資訊。
量測作業是由計量符號表示，且一律會以實線) 的 (qubit 暫存器做為輸入，並輸出以雙線) 表示的傳統資訊 (。
具體而言，這類 subcircuit 看起來像這樣：

<!--- ![](.\media\7.svg) ---->
<!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：-->
![代表測量運算的符號](~/media/7.svg)

Q#針對此用途來執行[量值運算子](xref:microsoft.quantum.intrinsic.measure)。
如需詳細資訊，請參閱[測量的一節](xref:microsoft.quantum.libraries.standard.prelude#measurements)。

同樣地，subcircuit

<!--- ![](.\media\8.svg) --->
<!--找不到輕鬆地將其置中的方法 .。。可能需要延伸模組：-->
![代表受控制作業的線路圖表](~/media/8.svg)

提供受傳統方式控制的閘道，其中 $ G $ 適用于傳統控制位的值為 $ 1 $ 。

## <a name="teleportation-circuit-diagram"></a>Teleportation 線路圖表
量子 teleportation 可能是用來說明這些元件的最佳量子演算法。
您可以學習使用對應的[量子 Kata](xref:microsoft.quantum.overview.katas)量子 teleportation，這是一種在量子電腦中移動資料的方法， (或甚至是在配量網路中的較遠量子電腦之間，) 透過使用會任何牽連和測量。
有趣的是，它實際上能夠將量子狀態（也就是指定 qubit 中的值）從一個 qubit 移到另一個，而不用知道 qubit 的值是什麼！
這是通訊協定根據量子機制的法律而必須運作的必要條件。
下面提供量子 teleportation 線路;我們也會提供已標注的電路版本，以說明如何讀取配量線路。

<!--- ![](.\media\tp2.svg) { 寬度 = 50%} --->
![量子 teleportation 線路](~/media/tp2.svg)
