---
標題：量子運算詞彙描述：量子運算中所使用之常用詞彙、動作和物件的詞彙。
作者： bradben ms. 作者： v-benbra ms. date： 9/1/2020 ms. 主題：文章 uid： microsoft. 量子. 詞彙 no loc：
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

# <a name="quantum-computing-glossary"></a>量子運算詞彙

## <a name="adjoint"></a>伴隨

[運算](xref:microsoft.quantum.glossary#operation)的複數共軛。 針對執行 [單一](xref:microsoft.quantum.glossary#unitary-operator) 運算子的作業，adjoint 是作業的反向作業，並以 dagger 符號表示。 例如，如果作業 `U` 代表單一運算子 $ U $ ，則 `Adjoint U` 表示 $ u ^ \dagger $ 。 如需詳細資訊，請參閱 [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。

## <a name="ancilla"></a>Ancilla

一種 [量子位](xref:microsoft.quantum.glossary#qubit) ，可作為量子電腦的暫存記憶體，並視需要進行配置和解除配置。  如需詳細資訊，請參閱 [多個量子位](xref:microsoft.quantum.concepts.multiple-qubits)。

## <a name="bell-state"></a>鐘州

四個特定充分中的其中一個 [纏結](xref:microsoft.quantum.glossary#entanglement)兩個量子位的 [量子狀態](xref:microsoft.quantum.glossary#quantum-state) 。 四個狀態定義為 $ \ket { \beta _ { ij } } = (\mathbb { I } \otimes X ^ iZ ^ j)  (\ket { 00 }  +  \ket { 11 }) / \sqrt { 2 } $ 。 鐘狀態也稱為 [EPR](xref:microsoft.quantum.glossary#epr-pair)組。

## <a name="bloch-sphere"></a>布洛赫球體

以圖形表示的單一[量子位](xref:microsoft.quantum.glossary#qubit)[量子狀態](xref:microsoft.quantum.glossary#quantum-state)，作為三維單位球體中的點。 如需詳細資訊，請參閱  [使用布洛赫球體視覺化量子位和轉換](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)。

## <a name="callable"></a>調用

語言[中的作業或](xref:microsoft.quantum.glossary#operation)[函數](xref:microsoft.quantum.glossary#function) Q# 。 如需詳細資訊，請參閱 [作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="clifford-group"></a>Clifford 群組

一組作業，會佔用 [布洛赫球體](xref:microsoft.quantum.glossary#bloch-sphere) 的 octants，以及 [Pauli 運算子](xref:microsoft.quantum.glossary#pauli-operators)的效果排列。 這些包括作業[ $ X $ ](xref:microsoft.quantum.intrinsic.x)、 [ $ Y $ ](xref:microsoft.quantum.intrinsic.y)、 [ $ Z $ ](xref:microsoft.quantum.intrinsic.z)、 [ $ H $ ](xref:microsoft.quantum.intrinsic.h)和[ $ S $ ](xref:microsoft.quantum.intrinsic.s)。

## <a name="controlled"></a>控制

將一或多個[量子位](xref:microsoft.quantum.glossary#qubit)做為目標[作業的啟用程式的量子作業](xref:microsoft.quantum.glossary#operation)。 如需詳細資訊，請參閱 [控制和 adjoint 作業](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。

## <a name="dirac-notation"></a>Dirac 標記法

符號縮寫，可簡化 [量子狀態](xref:microsoft.quantum.glossary#quantum-state)的標記法，也稱為 *bra ket* 標記法。  *Bra*部分代表一個資料列向量，例如，一個 $ \bra { } = \begin{bmatrix} { _2， } & { } \end{bmatrix} $ 而*ket*部分代表一個資料行向量（ $ \ket { b } = \begin{bmatrix} b { _1 } \\\\ b _2） { } \end{bmatrix} $ 。 如需詳細資訊，請參閱 [Dirac 標記法](xref:microsoft.quantum.concepts.dirac)。

## <a name="eigenvalue"></a>特徵

轉換的應用程式會變更給定轉換的 [eigenvector](xref:microsoft.quantum.glossary#eigenvector) 幅度變更的因素。  假設有一個正方形矩陣 $ M $ 和一個 eigenvector $ v $ ，則 $ 是 Mv = cv $ ，其中 $ c $ 是 eigenvalue，而且可以是任何引數的複數。 如需詳細資訊，請參閱 [Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="eigenvector"></a>Eigenvector

由指定的轉換變更方向，而且其幅度由對應于該向量 [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)之因數變更的向量。 假設有一個正方形矩陣 $ M $ 和一個 eigenvalue $ c $ ，then $ Mv = cv $ ，其中 $ v $ 是矩陣的 eigenvector，而且可以是任何引數的複數。 如需詳細資訊，請參閱 [Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="entanglement"></a>糾纏

量子粒子（例如 [量子位](xref:microsoft.quantum.glossary#qubit)）可以連接或 *纏結* ，使其無法彼此分開描述。 它們的測量結果會相互關聯，即使它們會無限地分開。 纏結對於 [測量](xref:microsoft.quantum.glossary#measurement) 量子位的 [狀態](xref:microsoft.quantum.glossary#quantum-state) 而言是不可或缺的。  如需詳細資訊，請參閱 [Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="epr-pair"></a>EPR 配對

四個特定充分中的其中一個纏結兩個[量子位](xref:microsoft.quantum.glossary#qubit)的[量子狀態](xref:microsoft.quantum.glossary#quantum-state)。 四個狀態定義為 $ \ket { \beta _ { ij } } = (\mathbb { 1 } \otimes X ^ iZ ^ j)  (\ket { 00 }  +  \ket { 11 }) / \sqrt { 2 } $ 。 EPR 配對也稱為 [鐘州](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>演化

[量子狀態](xref:microsoft.quantum.glossary#quantum-state)如何隨著時間變更。 如需詳細資訊，請參閱 [矩陣指數](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)。

## <a name="function"></a>函式
Q#語言中純傳統 (非量子) 的副程式類型。 雖然函式是在量子演算法內使用，但無法對 [量子位](xref:microsoft.quantum.glossary#qubit) 或呼叫 [作業](xref:microsoft.quantum.glossary#operation)採取行動。 如需詳細資訊，請參閱 [作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="gate"></a>門

量子 [運算](xref:microsoft.quantum.glossary#operation)的舊版詞彙，以傳統邏輯閘道的概念為基礎。 [量子電路](xref:microsoft.quantum.glossary#quantum-circuit-diagram)是閘道 (或作業) 的網路，根據傳統邏輯電路的類似概念。

## <a name="global-phase"></a>全域階段

當兩個[狀態](xref:microsoft.quantum.glossary#quantum-state)的最大值與複數 e ^ i 的倍數相同時 $ ，就 { \phi } $ 表示不同于全域階段。 不同于本機階段，無法透過任何 [測量](xref:microsoft.quantum.glossary#measurement)觀察到全域階段。 如需詳細資訊，請參閱 [量子位](xref:microsoft.quantum.concepts.qubit)。

## <a name="hadamard"></a>Hadamard

Hadamard 作業 (也稱為 Hadamard 閘道或轉換) 作用於單一[量子位](xref:microsoft.quantum.glossary#qubit)，並將其放入偶數[迭加](xref:microsoft.quantum.glossary#superposition) $ \ket { 0 } $ 或 $ \ket { 1 （ } $ 如果量子位一開始是 $ \ket { 0 } $ 狀態）。 在中 Q# ，這項作業會由預先定義的作業套用 [`H`](xref:microsoft.quantum.intrinsic.h) 。

## <a name="immutable"></a>固定

無法變更其值的變數。 中的不可變變數 Q# 是使用關鍵字來建立 `let` 。 若要宣告 *可* 變更的變數，請使用 [mutable](xref:microsoft.quantum.glossary#immutable) 關鍵字來宣告和 `set` 關鍵字以修改值。 

## <a name="measurement"></a>測量

[量子位](xref:microsoft.quantum.glossary#qubit) (或一組量子位) 的操作，這會產生觀察結果，實際上是取得傳統位。 如需詳細資訊，請參閱 [量子位](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)。

## <a name="mutable"></a>可變動

變數，其值在建立之後可能會變更。 中的 Q# 可變動變數是使用關鍵字來宣告 `mutable` ，並且使用 `set` 關鍵字進行修改。 使用關鍵字建立的變數 `let` 是 [不可變](xref:microsoft.quantum.glossary#immutable) 的，且其值無法變更。

## <a name="namespace"></a>命名空間

相關名稱集合的標籤 (例如、[作業](xref:microsoft.quantum.glossary#operation) [、函](xref:microsoft.quantum.glossary#function)[式和使用者定義型](xref:microsoft.quantum.glossary#user-defined-type)別) 。 例如，命名空間（namespace） [。準備](xref:microsoft.quantum.preparation) 標記標準程式庫中定義的所有符號，有助於準備初始狀態。

## <a name="operation"></a>作業

中量子計算的基本單位 Q# 。 它大致上相當於 C、c + + 或 Python 中的函式，或是 c # 或 JAVA 中的靜態方法。 如需詳細資訊，請參閱 [作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="operator-application"></a>操作員應用程式

執行量子運算。 這通常會將單一矩陣套用至目前的量子狀態向量。

## <a name="oracle"></a>Oracle

在執行時間將資料相依資訊提供給量子演算法的副程式。 一般來說，其目標是要提供對應至迭加中輸入的輸出 [迭加](xref:microsoft.quantum.glossary#superposition) 。 如需詳細資訊，請參閱 [oracle](xref:microsoft.quantum.libraries.data-structures#oracles)。

## <a name="partial-application"></a>部分應用程式

呼叫[不含](xref:microsoft.quantum.glossary#operation)所有必要輸入的[函數](xref:microsoft.quantum.glossary#function)或作業。 這 [會傳回新的可](xref:microsoft.quantum.glossary#callable) 呼叫，只需要在未來應用程式中提供的底線)  (所表示的遺漏參數。 例如，假設有個函式， `MyFunc(x : int, y : int) : int {return x + y;}` 您可以將它部分套用至新的函式 `let NewFunc = MyFunc(_, 3)` 。 然後，您可以稍後再使用遺漏的參數 `NewFunc(2)` （傳回值 *5*）來呼叫新的函式。  如需詳細資訊，請參閱 [部分應用程式](xref:microsoft.quantum.guide.operationsfunctions#partial-application)。

## <a name="pauli-operators"></a>Pauli 運算子

一組 3 2 x 2 個單一矩陣 `X` ，稱為 `Y` 和 `Z` 量子運算。 身分識別矩陣（ $ I $ ）通常也包含在集合中。  $I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} $ 、 $ X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} $ 、 $ Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix} $ 、 $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} $ 。   如需詳細資訊，請參閱 [單一量子位作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。

## <a name="quantum-circuit-diagram"></a>量子電路圖

一種方法，以圖形方式呈現簡單量副程式的 [作業](xref:microsoft.quantum.glossary#operation) (或網 [關](xref:microsoft.quantum.glossary#gate)) 的順序，例如 

![範例電路圖](~/media/qpe.png). 

如需詳細資訊，請參閱 [量子線路](xref:microsoft.quantum.concepts.circuits)。

## <a name="quantum-libraries"></a>量子程式庫

用於建立程式之[functions](xref:microsoft.quantum.glossary#function) [作業](xref:microsoft.quantum.glossary#operation)、函[式和使用者定義型](xref:microsoft.quantum.glossary#user-defined-type)別的集合 Q# 。 預設會安裝 [標準程式庫](xref:microsoft.quantum.libraries.standard.intro) 。 其他可用的程式庫有 [化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro)、 [數值](xref:microsoft.quantum.numerics.intro) 程式庫和 [機器學習程式庫](xref:microsoft.quantum.machine-learning.concepts.intro)。

## <a name="quantum-state"></a>量子狀態

隔離式量子系統的精確狀態，可從中解壓縮 [測量](xref:microsoft.quantum.glossary#measurement) 機率。 在量子運算中，量子模擬器會使用這項資訊來模擬量子位回應作業的方式。 如需詳細資訊，請參閱 [量子位](xref:microsoft.quantum.concepts.qubit)。

## <a name="qubit"></a>量子

量子資訊的基本單位，類似于傳統運算中的 *一點* 。 如需詳細資訊，請參閱 [量子位](xref:microsoft.quantum.concepts.qubit)。

## <a name="repeat-until-success"></a>重複直到成功

機率成功的量子演算法。 失敗時，常式會重試，直到成功 (或達到) 的限制為止。 如需詳細資訊，請參閱在 [成功 (Ru 之前重複執行) ](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>標準程式庫

在安裝期間與編譯器一起安裝的[作業](xref:microsoft.quantum.glossary#operation)、函式[和](xref:microsoft.quantum.glossary#function)[使用者定義類型](xref:microsoft.quantum.glossary#user-defined-type) Q# 。 標準程式庫的執行與目的電腦無關。 如需詳細資訊，請參閱 [標準程式庫](xref:microsoft.quantum.libraries.standard.intro)。

## <a name="superposition"></a>疊加

量子運算中的概念是，[量子位](xref:microsoft.quantum.glossary#qubit)是兩個狀態（ $ \ket { 0 } $ 和 $ \ket { 1 } $ ） [measured](xref:microsoft.quantum.glossary#measurement)的線性組合，直到測量為止。  如需詳細資訊，請參閱 [瞭解量子](xref:microsoft.quantum.overview.understanding)運算。

## <a name="target-machine"></a>目的電腦

將抽象量副程式減少到硬體或模擬的編譯目標。 這通常包含許多用途的重新撰寫，包括閘道更換、錯誤修正的編碼、幾何版面配置等等。 如需詳細資訊，請參閱 [量子模擬器和主應用程式](xref:microsoft.quantum.machines)。

## <a name="teleportation"></a>遙傳

一種方法，可使用[纏結](xref:microsoft.quantum.glossary#entanglement)和[測量](xref:microsoft.quantum.glossary#measurement)，將一個[量子位](xref:microsoft.quantum.glossary#qubit)的資料（或[量子狀態](xref:microsoft.quantum.glossary#quantum-state)）從一個位置重新產生到另一個位置，而不需要實際移動量子位。  如需詳細資訊，請參閱量子[Katas](xref:microsoft.quantum.overview.katas)的[量子線路](xref:microsoft.quantum.concepts.circuits)和個別的 kata。

## <a name="tuple"></a>Tuple

以逗號分隔值的集合，可作為單一值。 元組的 *型* 別是由它所包含的數值型別所定義。 在中 Q# ，元組是 [不可變](xref:microsoft.quantum.glossary#immutable) 的，而且可以嵌套、包含陣列或用於陣列中。 如需詳細資訊，請參閱 [元組類型](xref:microsoft.quantum.guide.types#tuple-types)。

## <a name="unitary-operator"></a>單一運算子

反轉等於其[adjoint](xref:microsoft.quantum.glossary#adjoint)的運算子，亦即， $ UU ^ { \dagger } = \id $ 。

## <a name="user-defined-type"></a>使用者定義型別

內建或先前定義型別的集合，這些型別可能稱為單一單位。 如需詳細資訊，請參閱 [使用者定義類型](xref:microsoft.quantum.guide.types#user-defined-types)。