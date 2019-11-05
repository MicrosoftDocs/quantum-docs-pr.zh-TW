---
title: 'Q # 標準程式庫-序言 |Microsoft Docs'
description: 'Q # 標準程式庫-序言'
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: dddb3d4a5ebcdca16da41a5ae5520d98ea900a7f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73183228"
---
# <a name="the-prelude"></a>序言 #

包含在「配量開發工具組」中的 Q # 編譯器和目的電腦，會提供一組內建函式和作業，可在 Q # 中撰寫量副程式時使用。

## <a name="intrinsic-operations-and-functions"></a>內部作業和函數 ##

標準程式庫中定義的內建作業，大致分為數個類別的其中一種：

- 在 <xref:microsoft.quantum.core> 命名空間中收集的基本傳統函數。
- 代表由[Clifford 和 $T $ 閘道](xref:microsoft.quantum.concepts.qubit)組成之 unitaries 的作業。
- 代表各種運算子旋轉的作業。
- 執行測量的作業。

由於 Clifford + $T $ 閘道集是適用于配量運算的[通用](xref:microsoft.quantum.concepts.multiple-qubits)集合，因此這些作業已足以在 negligibly 小型錯誤中執行任何量子演算法。
藉由提供旋轉，Q # 可讓程式設計人員在單一 qubit 單一和 CNOT-CONTAINS 閘道程式庫中工作。 此程式庫較容易考慮，因為它不需要程式設計人員直接表達 Clifford + $T $ 分解，而且因為有高效率的方法可將單一 qubit unitaries 編譯成 Clifford 和 $T $ 閘道（請參閱[這裡](xref:microsoft.quantum.more-information)以取得詳細資訊）。

可能的話，在序言中定義的作業（作用於 qubits）允許套用 `Controlled` 變異，如此目的電腦就會執行適當的分解。

在序言的這個部分中定義的許多函式和作業都是在 @"microsoft.quantum.intrinsic" 命名空間中，因此大部分的 Q # 來源檔案在初始命名空間宣告之後都會有 `open Microsoft.Quantum.Intrinsic;` 指示詞。
<xref:microsoft.quantum.core> 命名空間會自動開啟，因此 <xref:microsoft.quantum.core.length> 這類函式不需要 `open` 語句即可使用。

### <a name="common-single-qubit-unitary-operations"></a>一般單一 Qubit 單一作業 ###

序言也會定義許多常見[的單一 qubit 作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。
所有這些作業都允許 `Controlled` 和 `Adjoint` 函子。

#### <a name="pauli-operators"></a>Pauli 運算子 ####

<xref:microsoft.quantum.intrinsic.x> 作業會實 Pauli $X $ 運算子。
這有時候也稱為 `NOT` 閘道。
它具有簽章 `(Qubit => Unit is Adj + Ctl)`。
它會對應至單一 qubit 單一：

\begin{equation} \begin{bmatrix} 0 & 1 \\\\% FIXME：這目前使用 quadwhack 的駭客攻擊。
1 & 0 \end{bmatrix} \end{equation}

<xref:microsoft.quantum.intrinsic.y> 作業會實 Pauli $Y $ 運算子。
它具有簽章 `(Qubit => Unit is Adj + Ctl)`。
它會對應至單一 qubit 單一：

\begin{equation} \begin{bmatrix} 0 &-i \\\\% FIXME：這目前使用 quadwhack 的駭客攻擊。
我 & 0 \end{bmatrix} \end{equation}

<xref:microsoft.quantum.intrinsic.z> 作業會實 Pauli $Z $ 運算子。
它具有簽章 `(Qubit => Unit is Adj + Ctl)`。
它會對應至單一 qubit 單一：

\begin{equation} \begin{bmatrix} 1 & 0 \\\\% FIXME：這目前使用 quadwhack 的駭客攻擊。
0 &-1 \end{bmatrix} \end{equation}

以下是對應至[Bloch 球體](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)的轉換（每個案例中的旋轉軸會反白顯示為紅色）：

![對應至 Bloch 球體的 Pauli 作業](~/media/prelude_pauliBloch.png)

請務必注意，將相同的 Pauli 閘道套用到相同的 qubit 兩次會取消作業（因為您現在已在表面上執行完整的2π（360°）旋轉以 Bloch 球體，因而在起點處回傳）。 這會將我們帶入下列身分識別：

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

這可以在 Bloch 球體上 visualised：

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>其他單一 Qubit Cliffords ####

<xref:microsoft.quantum.intrinsic.h> 作業會執行 Hadamard 閘道。
這會交換目標 qubit 的 Pauli $X $ 和 $Z $ 軸，因此 $H \ket{0} = \ket{+} \mathrel{： =} （\ket{0} + \ket{1}）/\sqrt{2}$ and $H \ket{+} = \ket{0}$。
它具有 `(Qubit => Unit is Adj + Ctl)`的簽章，並對應至單一 qubit 的單一元件：

\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME：這目前使用 quadwhack 的駭客攻擊。
1 &-1 \end{bmatrix} \end{equation}

Hadamard 閘道特別重要，因為它可以用來建立 $ \ket{0}$ 和 $ \ket{1}$ 狀態的重迭。 在 Bloch 球體標記法中，最簡單的方式是將此視為 X 軸繞 $ \pi $ 弧度（$ 180 ^ \circ $）旋轉的 $ \ket{\psi} $，後面接著以 $ \ pi/2 $ 弧度（$ 90 ^ \circ $）圍繞 y 軸的（順時針）旋轉：

![對應至 Bloch 球體的 Hadamard 作業](~/media/prelude_hadamardBloch.png)

<xref:microsoft.quantum.intrinsic.s> 作業會執行階段閘道 $S $。
這是 Pauli $Z $ 作業的矩陣平方根。
也就是 $S ^ 2 = Z $。
它具有 `(Qubit => Unit is Adj + Ctl)`的簽章，並對應至單一 qubit 的單一元件：

\begin{equation} \begin{bmatrix} 1 & 0 \\\\% FIXME：這目前使用 quadwhack 的駭客攻擊。
0 & i \end{bmatrix} \end{equation}

#### <a name="rotations"></a>輪替 ####

除了上述的 Pauli 和 Clifford 作業，Q # 序言也提供各種表達旋轉的方式。
如[單一 qubit 作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)中所述，旋轉的功能對量子演算法而言非常重要。

我們一開始先重新開機，我們可以使用 $H $ 和 $T $ 閘道來表示任何單一 qubit 作業，其中 $H $ 是 Hadamard 作業，其中 \begin{equation} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\\\% FIXME：這目前使用的是四回摧毀的駭客。
0 & e ^ {i \pi/4} \end{bmatrix} \end{equation} 這是 <xref:microsoft.quantum.intrinsic.s> 作業的平方根，因此 $T ^ 2 = S $。
$T $ 閘道接著由 <xref:microsoft.quantum.intrinsic.t> 作業執行，而且具有簽章 `(Qubit => Unit is Adj + Ctl)`，表示它是單一 qubit 上的單一作業。

雖然這是用來描述任何任意單一 qubit 作業的原則，但不同的目的電腦對於 Pauli 運算子的輪替可能會有更有效率的標記法，因此序言包含各種不同的方式來 convienently表達這類旋轉。
其中最基本的就是 <xref:microsoft.quantum.intrinsic.r> 作業，它會在指定的 Pauli 軸上執行旋轉、\begin{equation} R （\sigma、\phi） \mathrel{： =} \exp （-i \phi \sigma/2）、\end{equation}，其中 $ \sigma $ 是 Pauli 運算子，$ \phi $ 是一個角度，其中 $\exp $ 代表矩陣指數。
它具有簽章 `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`，其中輸入的前兩個部分代表指定單一運算子 $R （\sigma，\phi） $ 所需的傳統引數 $ \sigma $ 和 $ \phi $。
我們可以部分套用 $ \sigma $ 和 $ \phi $，以取得其類型為單一 qubit 單一的作業。
例如，`R(PauliZ, PI() / 4, _)` 的類型 `(Qubit => Unit is Adj + Ctl)`。

> [!NOTE]
> <xref:microsoft.quantum.intrinsic.r> 作業會將輸入角度除以2，並將它乘以-1。
> 針對 $Z $ 旋轉，這表示 $ \ket{0}$ eigenstate 會由 $-\phi/$2 旋轉，而 $ \ket{1}$ eigenstate 會旋轉 $ \phi/$2，讓 $ \ket{1}$ eigenstate 以 $ \phi $ 旋轉，相對於 $ \ket{0}$ eigenstate。
>
> 特別是，這表示 `T` 和 `R(PauliZ, PI() / 8, _)` 只有一個不相關的[全域階段](xref:microsoft.quantum.glossary#global-phase)才有差異。
> 基於這個理由，$T $ 有時稱為 $ \frac{\pi}{8}$-閘道。
>
> 另請注意，旋轉 `PauliI` 只會套用 $ \phi/$2 的全域階段。 雖然這類階段並不相關，但是在[概念檔](xref:microsoft.quantum.concepts.qubit)中有人認為，它們與控制的 `PauliI` 旋轉相關。

在量子演算法中，以 dyadic 的分數表示旋轉通常很有用，例如，$ \phi = \pi k/2 ^ n $ 適用于某些 $k \in \mathbb{Z} $ 和 $n \in \mathbb{N} $。
<xref:microsoft.quantum.intrinsic.rfrac> 作業會使用此慣例，在指定的 Pauli 軸周圍執行旋轉。
它與 <xref:microsoft.quantum.intrinsic.r> 不同之處在于，旋轉角度會指定為 `Int`類型的兩個輸入，並以 dyadic 的分數來轉譯。
因此，`RFrac` 具有簽章 `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`。
它會執行單一 qubit 的單一 $ \exp （i \pi k \sigma/2 ^ n） $，其中 $ \sigma $ 是對應至第一個引數的 Pauli 矩陣，$k $ 是第二個引數，而 $n $ 是第三個引數。
`RFrac(_,k,n,_)` 與 `R(_,-πk/2^n,_)`相同;請注意，角度是分數的*負值*。

<xref:microsoft.quantum.intrinsic.rx> 作業會針對 Pauli $X $ 軸執行旋轉。
它具有簽章 `((Double, Qubit) => Unit is Adj + Ctl)`。
`Rx(_, _)` 與 `R(PauliX, _, _)`相同。

<xref:microsoft.quantum.intrinsic.ry> 作業會針對 Pauli $Y $ 軸執行旋轉。
它具有簽章 `((Double, Qubit) => Unit is Adj + Ctl)`。
`Ry(_, _)` 與 `R(PauliY,_ , _)`相同。

<xref:microsoft.quantum.intrinsic.rz> 作業會針對 Pauli $Z $ 軸執行旋轉。
它具有簽章 `((Double, Qubit) => Unit is Adj + Ctl)`。
`Rz(_, _)` 與 `R(PauliZ, _, _)`相同。

<xref:microsoft.quantum.intrinsic.r1> 作業會依指定的量來執行旋轉，{1}$ （$Z $ 的 $-$1 eigenstate）。
它具有簽章 `((Double, Qubit) => Unit is Adj + Ctl)`。
`R1(phi,_)` 與 `R(PauliZ,phi,_)` 後面接著 `R(PauliI,-phi,_)`。

<xref:microsoft.quantum.intrinsic.r1frac> 作業會依照 Z = 1 eigenstate 的指定數量來執行小數旋轉。
它具有簽章 `((Int,Int, Qubit) => Unit is Adj + Ctl)`。
`R1Frac(k,n,_)` 與 `RFrac(PauliZ,-k.n+1,_)` 後面接著 `RFrac(PauliI,k,n+1,_)`。

對應至 Bloch 球體的旋轉作業範例（在此實例中的 Pauli $Z $ 軸周圍）如下所示：

![對應至 Bloch 球體的旋轉作業](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>多 Qubit 作業 ####

除了上述的單一 qubit 作業，序言也會定義數個多 qubit 的作業。

首先，<xref:microsoft.quantum.intrinsic.cnot> 作業會執行標準控制`NOT` 閘道，\begin{equation} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1\\\\ 0 & 0 & 1 & 0 \end{bmatrix}。
\end{equation} 它具有簽章 `((Qubit, Qubit) => Unit is Adj + Ctl)`，代表 $ \operatorname{CNOT} $ act unitarily 在兩個個別 qubits 上。
`CNOT(q1, q2)` 與 `(Controlled X)([q1], q2)`相同。
由於 `Controlled` 仿函數允許在暫存器上控制，因此我們使用陣列常值 `[q1]` 來表示我們只需要一個控制項。

<xref:microsoft.quantum.intrinsic.ccnot> 作業會執行雙向控制的 NOT 閘道，有時也稱為 Toffoli 閘道。
它具有簽章 `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`。
`CCNOT(q1, q2, q3)` 與 `(Controlled X)([q1, q2], q3)`相同。

<xref:microsoft.quantum.intrinsic.swap> 作業會交換兩個 qubits 的量子狀態。
也就是說，它會執行單一矩陣 \begin{equation} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 &0 & 0 & 1 \end{bmatrix}。
\end{equation} 它的簽章 `((Qubit, Qubit) => Unit is Adj + Ctl)`。
`SWAP(q1,q2)` 相當於 `CNOT(q1, q2)` 後面接著 `CNOT(q2, q1)`，然後 `CNOT(q1, q2)`。

> [!NOTE]
> 交換網*關與重新*排列具有類型 `Qubit[]`之變數的元素不同。
> 套用 `SWAP(q1, q2)` 會導致 `q1` 和 `q2`所參考之 qubits 狀態的變更，而 `let swappedRegister = [q2, q1];` 只會影響我們參考這些 qubits 的方式。
> 此外，`(Controlled SWAP)([q0], (q1, q2))` 可讓 `SWAP` 在第三個 qubit 的狀態下進行條件，我們無法藉由重新排列元素來表示。
> 受控制的交換閘道（也稱為 Fredkin 閘道）功能強大，足以包含所有的傳統計算。

最後，序言會提供兩個作業來代表多 qubit Pauli 運算子的指數。
<xref:microsoft.quantum.intrinsic.exp> 作業會根據 Pauli 矩陣的張量產品執行迴圈，如多 qubit 的單一 \begin{equation} \operatorname{Exp} （\vec{\sigma}，\phi） \mathrel{： =} \exp\left （i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right）、\end{equation}，其中 $ \vec{\sigma} = （\ sigma_0，\ sigma_1，\dots ..，\ sigma_n） $ 是一系列的單一 qubit Pauli 運算子，其中 $ \phi $ 是角度。
`Exp` 旋轉會將 $ \vec{\sigma} $ 表示為 `Pauli` 元素的陣列，使其具有簽章 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`。

<xref:microsoft.quantum.intrinsic.expfrac> 作業會使用上述所討論的 dyadic 分數標記法來執行相同的旋轉。
它具有簽章 `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`。

> [!WARNING]
> Pauli 運算子的張量產品指數與指數運算子 Pauli 的張量產品不同。
> 也就是說，$e ^ {i （Z \otimes Z） \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $。

### <a name="measurements"></a>測量 ###

測量時，所測量之運算子的 + 1 eigenvalue 會對應至 `Zero` 的結果，而-1 eigenvalue 為 `One` 的結果。

> [!NOTE]
> 雖然此慣例看似奇怪，但它有兩個非常好用的優點。
> 首先，觀察結果 $ \ket{0}$ 是以 `Result` 值 `Zero`表示，同時觀察 $ \ket{1}$ 會對應至 `One`。
> 其次，我們可以寫出 eigenvalue $ \lambda $ 的對應結果，$r $ is $ \lambda = （-1） ^ r $。

量測作業不支援 `Adjoint` 或 `Controlled` 仿函數。

<xref:microsoft.quantum.intrinsic.measure> 作業會在 Pauli 運算子的指定產品中，執行一或多個 qubits 的聯合測量。
如果 Pauli 陣列和 qubit 陣列的長度不同，則作業會失敗。
`Measure` 具有簽章 `((Pauli[], Qubit[]) => Result)`。

請注意，聯合測量與個別測量每個 qubit 的方式不同。
例如，請考慮 state $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$。
逐一測量 $Z _0 $ 和 $Z _1 $，我們得到 $r _0 = $1 和 $r _1 = $1 的結果。
測量 $Z _0 Z_1 $）時，我們取得單一結果 $r _ {\textrm{joint}} = $0，代表 $ \ket{11}$ 的 pairity 是正數。
以不同的方式放置 $ （-1） ^ {r_0 + r_1} = （-1） ^ r_ {\textrm{joint}}） $。
嚴重的是，因為我們*只*會從這項測量中學習同位檢查，所以會保留正則兩者的 2 2-qubit 狀態之間的重迭中所代表的任何量子資訊，$ \ket{00}$ 和 $ \ket{11}$。
此屬性稍後會很重要，因為我們會討論錯誤修正。

為了方便起見，序言也提供兩個其他作業來測量 qubits。
首先，由於執行單一 qubit 測量非常常見，序言會定義此案例的速記。
<xref:microsoft.quantum.intrinsic.m> 作業會測量單一 qubit 上的 Pauli $Z $ 運算子，並具有簽章 `(Qubit => Result)`。
`M(q)` 相當於 `Measure([PauliZ], [q])`。

<xref:microsoft.quantum.measurement.multim> 會*分別*測量每個 qubits 陣列的 Pauli $Z $ 運算子，傳回為每個 qubit 取得的 `Result` 值*陣列*。
在某些情況下，可以將此優化。 它具有簽章（`Qubit[] => Result[])`。
`MultiM(qs)` 相當於：

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>擴充功能和作業 ##

此外，序言會在 .NET 層級定義一組豐富的數學和類型轉換函式，以便在 Q # 程式碼中使用。
例如，<xref:microsoft.quantum.extensions.math> 命名空間會定義有用的作業，例如 <xref:microsoft.quantum.extensions.math.sin> 和 <xref:microsoft.quantum.extensions.math.log>。
配量開發工具組所提供的實現會使用傳統 .NET 基類庫，因此可能牽涉到配量程式與其傳統驅動程式之間的額外通訊往返。
雖然這不會對本機模擬器造成問題，但在使用遠端模擬器或實際硬體做為目的電腦時，這可能會造成效能問題。
話雖如此，個別目的電腦可以藉由使用更有效率的特定系統版本來覆寫這些作業，以降低對效能的影響。

### <a name="math"></a>運算式 ###

<xref:microsoft.quantum.extensions.math> 命名空間會從 .NET 基類庫的[`System.Math` 類別](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)提供許多有用的函式。
這些函式的使用方式與其他任何 Q # 函數相同：

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

其中 .NET 靜態方法已根據其引數的型別多載，相對應的 Q # 函式會以後置詞標注，以指出其輸入的型別：

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>位運算 ###

最後，<xref:microsoft.quantum.extensions.bitwise> 命名空間會提供幾個實用的函式，以透過位運算子來操作整數。
例如，<xref:microsoft.quantum.extensions.bitwise.parity> 會傳回整數的位同位檢查，做為另一個整數。
