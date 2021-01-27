---
title: QDK 中的內建作業和函數
description: 瞭解 QDK 中的內建作業和函式，包括傳統函數和單一、旋轉和測量作業。
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6ed5b1677a204b9425f229a3ea0855bb789f3f75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857194"
---
# <a name="the-prelude"></a>序言 #

Q#包含在量子開發工具組中的編譯器和目的電腦提供一組內建函式和作業，可在中撰寫量副程式時使用 Q# 。

## <a name="intrinsic-operations-and-functions"></a>內建作業和函數 ##

標準程式庫中定義的內建作業，大致屬於數個類別的其中一種：

- 在命名空間中收集的基本傳統函數 <xref:Microsoft.Quantum.Core> 。
- 代表由 [Clifford 和 $T $ 閘道](xref:microsoft.quantum.concepts.qubit)組成之 unitaries 的作業。
- 代表各種運算子之旋轉的作業。
- 執行測量的作業。

由於 Clifford + $T $ 閘道集是適用于量子運算的 [通用](xref:microsoft.quantum.concepts.multiple-qubits) ，因此這些作業足以大約在 negligibly small 錯誤內執行任何量子演算法。
藉由提供旋轉，可讓程式設計人員 Q# 在單一量子位的單一和 CNOT 閘道程式庫中工作。 此程式庫較容易考慮，因為它不需要程式設計人員直接表達 Clifford + $T $ 分解，也因為有高效率的方法可將單一量子位 unitaries 編譯成 Clifford 和 $T $ 閘道 (請參閱 [這裡](xref:microsoft.quantum.more-information) 以取得) 的詳細資訊。

可能的話，在序言中所定義的作業（在量子位上作用）允許套用 `Controlled` variant，讓目的電腦能夠執行適當的分解。

這部分序言中定義的許多函數和作業都在 @"microsoft.quantum.intrinsic" 命名空間中，因此大部分的 Q# 原始程式檔都會 `open Microsoft.Quantum.Intrinsic;` 緊接在初始命名空間宣告之後。
<xref:Microsoft.Quantum.Core>命名空間會自動開啟，如此一來，就 <xref:Microsoft.Quantum.Core.Length> 可以在沒有語句的情況下使用 `open` 。

### <a name="common-single-qubit-unitary-operations"></a>常見 Single-Qubit 單一作業 ###

序言也會定義許多常見 [的單一量子位作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。
所有這些作業都允許 `Controlled` 和 `Adjoint` 函子。

#### <a name="pauli-operators"></a>Pauli 運算子 ####

作業會實 <xref:Microsoft.Quantum.Intrinsic.X> Pauli $X $ 運算子。
這有時也稱為網 `NOT` 關。
它有簽章 `(Qubit => Unit is Adj + Ctl)` 。
它會對應至單一量子位的單一：

\begin{equation} \begin{bmatrix} 0 & 1 \\ \\ % FIXME：這目前使用 quadwhack 的駭客。
1 & 0 \end{bmatrix} \end{equation}

作業會實 <xref:Microsoft.Quantum.Intrinsic.Y> Pauli $Y $ 運算子。
它有簽章 `(Qubit => Unit is Adj + Ctl)` 。
它會對應至單一量子位的單一：

\begin{equation} \begin{bmatrix} 0 &-i \\ \\ % FIXME：這目前使用 quadwhack 的駭客。
我 & 0 \end{bmatrix} \end{equation}

作業會實 <xref:Microsoft.Quantum.Intrinsic.Z> Pauli $Z $ 運算子。
它有簽章 `(Qubit => Unit is Adj + Ctl)` 。
它會對應至單一量子位的單一：

\begin{equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：這目前使用 quadwhack 的駭客。
0 &-1 \end{bmatrix} \end{equation}

在下面，我們會看到對應至 [布洛赫球體](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (旋轉軸在每個案例中的旋轉軸會反白顯示紅色) ：

![Pauli 對應至布洛赫球體的作業](~/media/prelude_pauliBloch.png)

請務必注意，將相同的 Pauli 閘道套用兩次至相同的量子位會取消作業 (因為您現在已在表面上執行2π (360 °) 的完整旋轉，以) 的起點回來。 這會將我們帶入下列身分識別：

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

這可以在布洛赫球體上 visualised：

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>其他 Single-Qubit Cliffords ####

作業會執行 <xref:Microsoft.Quantum.Intrinsic.H> Hadamard 閘道。
這會交換目標量子位的 Pauli $X $ 和 $Z $ 座標軸，例如 $H \ket {0} = \ket{+} \mathrel{： =} ( \ket {0} + \ket {1}) /\sqrt {2} $ 和 $H \ket{+} = \ket {0} $。
它有 `(Qubit => Unit is Adj + Ctl)` 簽章，並且對應至單一量子位的單一：

\begin{equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % FIXME：這目前使用 quadwhack 的駭客。
1 &-1 \end{bmatrix} \end{equation}

Hadamard 閘道特別重要，因為它可以用來建立 $ \ket {0} $ 和 $ \ket {1} $ 狀態的迭加。 在布洛赫球體標記法中，最簡單的方式是將此視為圍繞 X 軸的 $ \ket{\psi} $ 左右旋轉 $ \pi $ 弧度 ($ 180 ^ \circ $) 後面接著 (順時針) 圍繞 y 軸旋轉 $ \ pi/2 $ 弧度 ($ 90 ^ \circ $) ：

![對應到布洛赫球體的 Hadamard 作業](~/media/prelude_hadamardBloch.png)

作業會 <xref:Microsoft.Quantum.Intrinsic.S> 將階段閘道 $S $。
這是 Pauli $Z $ 運算的矩陣平方根。
也就是說，$S ^ 2 = Z $。
它有 `(Qubit => Unit is Adj + Ctl)` 簽章，並且對應至單一量子位的單一：

\begin{equation} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：這目前使用 quadwhack 的駭客。
0 & i \end{bmatrix} \end{equation}

#### <a name="rotations"></a>輪替人員 ####

除了上述的 Pauli 和 Clifford 作業， Q# 序言也提供各種方式來表達旋轉。
如同在 [單一量子位作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)中所述，旋轉的能力對量子演算法而言很重要。

我們一開始會先重新叫用，我們可以使用 $H $ 和 $T $ 閘道來表達任何單一量子位作業，其中 $H $ 是 Hadamard 作業，其中 \begin{equation} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ % FIXME：這目前使用四次的摧毀駭客攻擊。
0 & e ^ {i \pi/4} \end{bmatrix} \end{equation} 這是運算的平方根 <xref:Microsoft.Quantum.Intrinsic.S> ，例如 $T ^ 2 = S $。
作業接著會執行 $T $ 閘道， <xref:Microsoft.Quantum.Intrinsic.T> 且具有簽章 `(Qubit => Unit is Adj + Ctl)` ，表示它是單一量子位的單一作業。

雖然這在主體中足以描述任何任意的單一量子位作業，但不同的目的電腦對於 Pauli 運算子的旋轉可能有更有效率的表示，因此序言包含各種不同的方式來 convienently 表示這類旋轉。
其中最基本的作業，是在 <xref:Microsoft.Quantum.Intrinsic.R> 指定的 Pauli 軸上實行旋轉、\Begin{equation} R ( \sigma、\phi) \mathrel{： =} \exp (-i \phi \sigma/2) 、\end{equation}，其中 $ \sigma $ 是 Pauli 運算子、$ \phi $ 是一個角度，其中 $ \exp $ 代表矩陣指數。
它有簽章 `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` ，其中輸入的前兩個部分代表 $R ( \sigma，\phi) $ 指定單一運算子所需的傳統引數 $ \sigma $ 和 $ \phi $。
我們可以將 $ \sigma $ 和 $ \phi $ 部分套用，以取得類型為單一量子位單一的作業。
例如， `R(PauliZ, PI() / 4, _)` 具有類型 `(Qubit => Unit is Adj + Ctl)` 。

> [!NOTE]
> 作業 <xref:Microsoft.Quantum.Intrinsic.R> 會將輸入角度除以2，並將它乘以-1。
> 針對 $Z $ 旋轉，這表示 $ \ket {0} $ eigenstate 會旋轉 $-\phi/$2，而 $ \ket {1} $ eigenstate 會旋轉 $ \phi/$2，如此一來，$ \ket {1} $ eigenstate 就會旋轉 $ \phi $ \ket $ eigenstate $ {0} 。
>
> 特別是，這表示 `T` 和 `R(PauliZ, PI() / 8, _)` 差異只在於不相關的 [全域階段](xref:microsoft.quantum.glossary#global-phase)。
> 基於這個理由，$T $ 有時也稱為 $ \frac{\pi} {8} $-閘道。
>
> 另外也請注意，您 `PauliI` 只需套用 $ \phi/$2 的全域階段。 雖然這類階段與 [概念檔](xref:microsoft.quantum.concepts.qubit)中的有人認為無關，但它們與受控制的 `PauliI` 旋轉相關。

在量子演算法內，以 dyadic 小數表示旋轉通常很有用，例如，某些 $k \in \mathbb{Z} $ 和 $n \in \mathbb{N} $ 的 $ \phi = \pi k/2 ^ n $。
作業會 <xref:Microsoft.Quantum.Intrinsic.RFrac> 使用此慣例來執行圍繞指定 Pauli 軸的旋轉。
其不同之處在于， <xref:Microsoft.Quantum.Intrinsic.R> 旋轉角度會指定為類型的兩個輸入，並被視為 `Int` dyadic 分數。
因此， `RFrac` 有簽章 `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` 。
它會實量子位單一的 $ \exp (i \pi k \sigma/2 ^ n) $，其中 $ \sigma $ 是對應于第一個引數的 Pauli 矩陣，$k $ 是第二個引數，而 $n $ 是第三個引數。
`RFrac(_,k,n,_)` 與相同， `R(_,-πk/2^n,_)` 請注意角度是分數的 *負值* 。

作業會在 <xref:Microsoft.Quantum.Intrinsic.Rx> Pauli $X $ 軸上實行旋轉。
它有簽章 `((Double, Qubit) => Unit is Adj + Ctl)` 。
`Rx(_, _)` 與 `R(PauliX, _, _)` 相同。

作業會在 <xref:Microsoft.Quantum.Intrinsic.Ry> Pauli $Y $ 軸上實行旋轉。
它有簽章 `((Double, Qubit) => Unit is Adj + Ctl)` 。
`Ry(_, _)` 與 `R(PauliY,_ , _)` 相同。

作業會在 <xref:Microsoft.Quantum.Intrinsic.Rz> Pauli $Z $ 軸上實行旋轉。
它有簽章 `((Double, Qubit) => Unit is Adj + Ctl)` 。
`Rz(_, _)` 與 `R(PauliZ, _, _)` 相同。

作業會 <xref:Microsoft.Quantum.Intrinsic.R1> 在 $ \ket {1} $ （$-$1 eigenstate of $Z $）上，以指定的數量來實行旋轉。
它有簽章 `((Double, Qubit) => Unit is Adj + Ctl)` 。
`R1(phi,_)` 與後面的相同 `R(PauliZ,phi,_)` `R(PauliI,-phi,_)` 。

作業會 <xref:Microsoft.Quantum.Intrinsic.R1Frac> 依 Z = 1 eigenstate 的給定數量來執行小數旋轉。
它有簽章 `((Int,Int, Qubit) => Unit is Adj + Ctl)` 。
`R1Frac(k,n,_)` 與後面的相同 `RFrac(PauliZ,-k.n+1,_)` `RFrac(PauliI,k,n+1,_)` 。

 (圍繞于 Pauli $Z $ 軸的旋轉作業範例，在此例中，) 對應到布洛赫球體的如下所示：

![對應至布洛赫球體的旋轉作業](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>多量子位作業 ####

除了上述的單一量子位作業之外，序言也會定義數個多量子位作業。

首先，此作業會 <xref:Microsoft.Quantum.Intrinsic.CNOT> 執行標準的控制-網 `NOT` 關 \begin{equation} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}。
\end{equation} 它有簽章 `((Qubit, Qubit) => Unit is Adj + Ctl)` ，代表在兩個個別量子位上的 $ \operatorname{CNOT} $ act unitarily。
`CNOT(q1, q2)` 與 `(Controlled X)([q1], q2)` 相同。
因為 `Controlled` 仿函數允許在暫存器上控制，所以我們會使用陣列常值 `[q1]` 來指出我們只想要一個控制項。

作業 <xref:Microsoft.Quantum.Intrinsic.CCNOT> 會執行雙向控制的非閘道，有時也稱為 Toffoli 閘道。
它有簽章 `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` 。
`CCNOT(q1, q2, q3)` 與 `(Controlled X)([q1, q2], q3)` 相同。

作業會 <xref:Microsoft.Quantum.Intrinsic.SWAP> 交換兩個量子位的量子狀態。
也就是說，它會實作為單一矩陣 \begin{equation} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}。
\end{equation} 它有簽章 `((Qubit, Qubit) => Unit is Adj + Ctl)` 。
`SWAP(q1,q2)` 相當於 `CNOT(q1, q2)` 後面接著 `CNOT(q2, q1)` ，then `CNOT(q1, q2)` 。

> [!NOTE]
> 交換網 *關與重新* 排列具有類型的變數元素不同 `Qubit[]` 。
> 套用 `SWAP(q1, q2)` 會導致和所參考之量子位狀態的變更 `q1` `q2` ，而 `let swappedRegister = [q2, q1];` 只會影響我們參考這些量子位的方式。
> 此外， `(Controlled SWAP)([q0], (q1, q2))` 也允許 `SWAP` 在第三個量子位的狀態下進行條件，而我們無法藉由重新排列元素來表示。
> 控制交換閘道（也稱為 Fredkin 閘道）的功能強大，足以包含所有傳統計算。

最後，序言會提供兩個作業來代表多量子位 Pauli 運算子的指數。
作業會 <xref:Microsoft.Quantum.Intrinsic.Exp> 根據 Pauli 矩陣的 tensor 乘積來執行旋轉。如多量子位的單一 \Begin{equation} \operatorname{Exp} ( \vec{\sigma}，\phi) \mathrel{： =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right) ，\end{equation} where $ \vec{\sigma} = ( \ sigma_0，\ sigma_1，\dots ..，\ sigma_n) $ 是一系列的單一量子位 Pauli 運算子，其中 $ \phi $ 是一個角度。
`Exp`旋轉會將 $ \vec{\sigma} $ 表示為元素陣列 `Pauli` ，使其具有簽章 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` 。

作業會 <xref:Microsoft.Quantum.Intrinsic.ExpFrac> 使用上述的 dyadic 分數標記法來執行相同的旋轉。
它有簽章 `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` 。

> [!WARNING]
> Pauli 運算子 tensor 產品的指數與指數 Pauli 運算子的 tensor 產品不同。
> 也就是說，$e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $。

### <a name="measurements"></a>量測 ###

測量時，所測量運算子的 + 1 eigenvalue 會對應至 `Zero` 結果，而-1 則會 eigenvalue 至 `One` 結果。

> [!NOTE]
> 雖然這個慣例看起來很奇怪，但是有兩個很好的優點。
> 首先，觀察結果 $ \ket {0} $ 是以 `Result` 值表示 `Zero` ，而觀察 $ \ket $ 則 {1} 對應于 `One` 。
> 其次，我們可以寫出 eigenvalue $ \lambda $ 對應到結果的結果 $r $ 是 $ \lambda = (-1) ^ r $。

測量作業不支援 `Adjoint` 和 `Controlled` 仿函數。

作業會 <xref:Microsoft.Quantum.Intrinsic.Measure> 在指定的 Pauli 運算子產品中，執行一或多個量子位的聯合度量。
如果 Pauli 陣列和量子位陣列的長度不同，則作業會失敗。
`Measure` 有簽章 `((Pauli[], Qubit[]) => Result)` 。

請注意，聯合測量與個別測量每個量子位不同。
例如，請考慮 state $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $。
測量 $Z 的每個 _0 $ 和 $Z _1 $，我們得到的結果 $r _0 = $1，$r _1 = $1。
不過，測量 $Z _0 Z_1 $，我們得到單一結果 $r _ {\textrm{joint}} = $0，代表 $ \ket $ 的 pairity {11} 是正面的。
以不同的方式放置，$ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}} ) $。
嚴重的，因為我們 *只* 會從這項測量中瞭解同位檢查，所以會保留在 2 2-量子位狀態的正同位（$ \ket {00} $ 和 $ \ket $）之間的迭加中所代表的任何量子資訊 {11} 。
稍後當我們討論錯誤修正時，這個屬性將會是不可或缺的。

為了方便起見，序言也提供兩個其他作業來測量量子位。
首先，由於執行單一量子位量值相當常見，因此序言會定義此案例的速記。
作業會 <xref:Microsoft.Quantum.Intrinsic.M> 測量單一量子位上的 Pauli $Z $ 運算子，並擁有簽章 `(Qubit => Result)` 。
`M(q)` 相當於 `Measure([PauliZ], [q])`。

會在 <xref:Microsoft.Quantum.Measurement.MultiM> 每個量子位陣列上 *分別* 測量 Pauli $Z $ 運算子，並傳回 `Result` 為每個量子位取得的值陣列。
在某些情況下，這可以進行優化。 它 (簽章 `Qubit[] => Result[])` 。
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

此外，序言會在 .NET 層級定義一組豐富的數學和類型轉換函式，以便在程式碼中使用 Q# 。
例如， <xref:Microsoft.Quantum.Math> 命名空間會定義有用的作業，例如 <xref:Microsoft.Quantum.Math.Sin> 和 <xref:Microsoft.Quantum.Math.Log> 。
量子開發工具組所提供的實使用傳統的 .NET 基類庫，因此可能會涉及量副程式與其傳統驅動程式之間的額外通訊往返。
雖然這不會對本機模擬器造成問題，但這可能是使用遠端模擬器或實際硬體做為目的電腦時的效能問題。
也就是說，個別的目的電腦可以藉由使用較有效率的版本來覆寫這些作業，以降低這項效能的影響。

### <a name="math"></a>數學 ###

<xref:Microsoft.Quantum.Math>命名空間提供來自 .net 基類庫[ `System.Math` 類別](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true)的許多實用功能。
這些函數的使用方式與任何其他函式相同 Q# ：

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

其中已根據其引數的型別多載 .NET 靜態方法，對應的函式 Q# 會加上後置詞，表示其輸入的類型：

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>位運算 ###

最後， <xref:Microsoft.Quantum.Bitwise> 命名空間提供數個實用的函式，可透過位運算子來操作整數。
例如，會傳回 <xref:Microsoft.Quantum.Bitwise.Parity> 整數的位同位做為另一個整數。
