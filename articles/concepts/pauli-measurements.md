---
title: Pauli 測量
description: 瞭解如何使用單一和多 qubit 的 Pauli 測量作業。
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269468"
---
# <a name="pauli-measurements"></a>Pauli 測量

在先前的討論中，我們著重于計算基礎測量。
事實上，從標記的角度來看，在計量運算中所發生的其他常見測量，在計算基礎測量方面很方便表達。
當您使用 Q # 時，您會遇到的最常見測量類型可能是*Pauli 測量*，這會將計算基礎測量一般化以包含其他基底的度量，以及不同 qubits 之間的同位檢查。
在這種情況下，通常會討論測量 Pauli 運算子，通常是 $X、Y、Z $ 或 $Z \otimes Z、x \otimes x、x \otimes Y 等等的運算子 $ 。

> [!TIP]
> 在 Q # 中，多 qubit 的 Pauli 運算子通常會由類型的陣列表示 `Pauli[]` 。
> 例如，若要代表 $X \otimes Z \otimes Y $ ，您可以使用陣列 `[PauliX, PauliZ, PauliY]` 。

討論 Pauli 運算子方面的測量，特別是在量子錯誤更正的子欄位中。
在 Q # 中，我們遵循類似的慣例。我們現在會說明這種替代的度量觀點。

在探究到如何思考 Pauli 測量的詳細資料之前，請考慮測量量子電腦內的單一 qubit 對量子狀態的作用。
假設我們有 $n $ qubit 的量子狀態，然後測量一個 qubit，立即將該狀態的一半，視為可能出現在其中的 $ 2 ^ n 個 $ 可能性。
換句話說，測量會將量子狀態投射到兩個半形的其中一個。
我們可以將我們認為測量的方式一般化，以反映此直覺。

為了簡潔地識別這些 subspaces，我們需要用來描述它們的語言。
描述兩個 subspaces 的其中一種方式，是透過只具有兩個唯一特徵值的矩陣來指定它們，慣例是 $ \pm 1 $ 。
如需以這種方式描述 subspaces 的簡單範例，請考慮 $Z $ ：

$ $ \begin{align}
  Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } 。
\end{align}
$$

藉由讀取 Pauli $Z 矩陣的對角線元素 $ ，我們可以看到 $Z $ 有兩個特徵向量、$ \ket{0 } $ 和 $ \ket{1 } $，以及對應的特徵值 $ \pm 1 $ 。
因此，如果我們測量 qubit 並取得 `Zero` （對應至 state $ \ket{0 } $），我們就知道 qubit 的狀態是 $Z 運算子的 $ + 1 $ eigenstate $ 。
同樣地，如果我們取得 `One` ，我們知道 qubit 的狀態是 $Z 的 $-1 $ eigenstate $ 。
此程式在 Pauli 測量的語言中稱為「測量 Pauli $Z」 $ ，完全等同于執行計算基礎測量。

任何 \times $ 屬於 $Z 單一轉換的 $2 2 矩陣也都 $ 符合此準則。
也就是說，我們也可以使用矩陣 $A = U ^ \dagger Z U $ ，其中 $U $ 是任何其他的單一矩陣，以便在其 $ \pm 1 特徵向量中定義度量的兩個結果 $ 。
Pauli 量值的標記法會藉由將 $X、Y、Z $ 度量識別為對等的測量，以取得 qubit 中的資訊，來參考這個單一等價項。
為了方便起見，以下提供這些測量。


|Pauli 測量  |單一轉換  |
|-------------------|------------------------|
| $Z$               | $ \boldone$             |
| $X$               | $H$                    |
| $Y$               | $HS ^ {\dagger}$         |

也就是說，使用這種語言，「量值 $Y」等同于套用 $ $HS ^ \dagger， $ 然後以計算為基礎，其中是內建 [`S`](xref:microsoft.quantum.intrinsic.s) 的量子作業，有時稱為「階段閘道」，而且可由單一矩陣模擬

$ $ \begin{align}
    S = \begin{bmatrix}
        1 & 0 \\ \\ 0 & i \end{ bmatrix } 。
\end{align}
$$

這也相當於將 $HS ^ \dagger 套用 $ 至量子狀態向量，然後測量 $Z $ ，讓下列作業相當於 `Measure([PauliY], [q])` ：

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

藉由轉換回計算基礎，即可找到正確的狀態，這是將 $SH 套用 $ 至量子狀態向量的數量; 在上述程式碼片段中，轉換回計算基礎的動作會透過使用區塊自動處理 `within … apply` 。

在 Q # 中，我們會假設結果---也就是，從與狀態互動時所解壓縮的傳統資訊---是由 `Result` 值 $j \in \\ {\Texttt{Zero } ，\texttt{One} $ 所指定， } \\ 指出結果是否在 $ 所測量 Pauli 運算子的 $ （-1） ^ j eigenspace 中。


## <a name="multiple-qubit-measurements"></a>多 qubit 測量

多 qubit Pauli 運算子的度量定義類似，如下所示：

$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 0&\\\\ 0 & -1&0 \\\\ 0&0&0&1 \end{bmatrix} 。
$$

因此，兩個 Pauli $Z 運算子的張量產品會 $ 形成由包含 $ + 1 $ 和 $-1 特徵值的兩個空格所組成的矩陣 $ 。
就像單一 qubit 的情況一樣，兩者都構成一半空間，這表示可存取的兩個向量空間一半屬於 $ + 1 $ eigenspace，而其餘一半則是 $-1 $ eigenspace。
一般來說，您可以從張量產品的定義中查看任何 Pauli-$Z 運算子的張量產品， $ 以及身分識別也會遵守這項功能。
例如，

$ $ \begin{align}
    Z \otimes \boldone = \begin{bmatrix}
        1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & \\ \\ 0 &-1 & 0 0 & 0 & \\ \\ 0 &-1 \end{ bmatrix } 。
\end{align}
$$

如前所述，這類矩陣的任何單一轉換也會描述由 $ \pm 1 特徵值標記的兩個半形 $ 。
例如， \otimes \otimes \otimes \otimes $ 從 $Z = HXH 的身分識別 $X X = H H （Z z） h h $ 。
與一個 qubit 的案例類似，所有的雙 qubit Pauli 量值都可以 \otimes $ $U 的 $4 \times 4 個 $ 單一矩陣的 $ $U ^ \Dagger （Z \id） U 寫入。 我們會列舉下表中的轉換。

> [!NOTE]
> 在下表中，我們使用 $ \operatorname{SWAP } $ 來表示矩陣 $ $ \begin{align}
>     \operatorname{SWAP } & = \left （\begin{matrix}
>         1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & \\ \\ 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{matrix } \right） \end{align}
> $ $ 用來模擬內部作業 [`SWAP`](xref:microsoft.quantum.intrinsic) 。

|Pauli 測量     |單一轉換  |
|----------------------|------------------------|
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $X \otimes \boldone$ | $H \otimes \boldone$ |
| $Y \otimes \boldone$ | $HS ^ \dagger \otimes \boldone$ |
| $ \boldone \otimes Z$ | $ \operatorname{SWAP}$ |
| $ \boldone \otimes X$ | $ （H \otimes \boldone） \operatorname{SWAP}$ |
| $ \boldone \otimes Y$ | $ （HS ^ \dagger \otimes \boldone） \operatorname{SWAP}$ |
| $Z \otimes Z$ | $ \operatorname{CNOT } \_ {10}$ |
| $X \otimes Z$ | $ \operatorname{CNOT } \_ {10 } （H \otimes \boldone） $ |
| $Y \otimes Z$ | $ \operatorname{CNOT } \_ {10 } （HS ^ \dagger \otimes \boldone） $ |
| $Z \otimes X$ | $ \operatorname{CNOT } \_ {10 } （\boldone \otimes H） $ |
| $X \otimes X$ | $ \operatorname{CNOT } \_ {10 } （h \otimes h） $ |
| $Y \otimes X$ | $ \operatorname{CNOT } \_ {10 } （HS ^ \dagger \otimes H） $ |
| $Z \otimes Y$ | $ \operatorname{CNOT } \_ {10 } （\boldone \otimes HS ^ \dagger） $ |
| $X \otimes Y$ | $ \operatorname{CNOT } \_ {10 } （H \otimes HS ^ \dagger） $ |
| $Y \otimes Y$ | $ \operatorname{CNOT } \_ {10 } （HS ^ \dagger \otimes hs ^ \dagger） $ |

在這裡，作業 [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) 會因為下列原因而出現。
不包含 $ \boldone 矩陣的每個 Pauli 量值， $ 都等同于由上而下的推理來 $Z \otimes Z $ 。
$Z Z 的特徵值 \otimes $ 只取決於組成每個計算基礎向量的 qubits 同位檢查，而受控制的非作業則是用來計算此同位，並將其儲存在第一位。
然後在測量第一個位之後，我們就可以復原結果半形的識別，這相當於測量 Pauli 運算子。

另一個注意事項：雖然假設測量 $Z \otimes Z $ 的 $Z 與依序測量 \otimes \mathbb{1 } $ 和 $ \mathbb{1 } \otimes Z 相同 $ ，但此假設為 false。
原因是測量 $Z \otimes Z $ 將量子狀態投射到這些運算子的 $ + 1 $ 或 $-1 $ eigenstate 中。
測量 $Z \otimes \mathbb{1 } $ 然後 $ \Mathbb{1 } \otimes Z 會 $ 先將量子狀態向量投射到 $Z \mathbb{1 $ 的一半 \otimes 空間 } ，然後再到 $ \mathbb{1 \otimes Z 的一半空間 } $ 。因為有四個計算基礎的向量，同時執行這兩個度量會將狀態縮減為四分之一空間，因而減少為單一計算基礎向量。

## <a name="correlations-between-qubits"></a>Qubits 之間的相互關聯
另一個查看 Pauli 矩陣（例如 $X X 或 $Z Z）之張量產品的方式， \otimes $ \otimes $ 是這些測量可讓您查看儲存在兩個 qubits 之間相互關聯的資訊。
測量 $X \otimes \id $ 可讓您查看本機儲存在第一個 qubit 中的資訊。
雖然這兩種類型的測量在量子運算中也同樣有價值，但前者也會照亮量子運算的威力。
它會顯示在量子運算中，您想要學習的資訊通常不會儲存在任何單一 qubit 中，而是會一次儲存在所有 qubits 中，因此，只有透過聯合測量來查看（例如 $Z \otimes Z），這項資訊才會 $ 成為資訊清單。

例如，在錯誤修正中，我們通常會想要瞭解在學習嘗試保護的狀態時，所發生的錯誤。
「[翻轉」程式碼範例會示範](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code)如何使用 $Z \otimes z \otimes \id $ 和 $ \id \Otimes z \otimes z 之類的測量來執行這項操作 $ 。
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

您也可以測量任意的 Pauli 運算子，例如 $X \otimes Y \Otimes Z \otimes \boldone $ 。
Pauli 運算子的所有這類張量產品只有兩個特徵值 $ \pm 1 $ ，而這兩個 eigenspaces 構成整個向量空間的半空格。
因此，它們會符合上面所述的需求。

在 Q # 中，這類測量結果會傳回 $j， $ 如果量值產生 eigenspace 的正負號 $ （-1） ^ j $ 。
將 Pauli 測量當做 Q # 中的內建功能很有説明，因為測量這類運算子需要較長的受控制（而非閘道）和基礎轉換鏈，以描述將作業當做 $ $Z $ 和 $ \id 的張量產品來表達作業所需的 diagonalizing $U 閘道 $ 。藉由指定您想要執行上述其中一項預先定義的測量，您就不需要擔心如何轉換基礎，讓計算基礎測量提供必要的資訊。
問 # 會自動為您處理所有必要的基礎轉換。
如需詳細資訊，請參閱 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 和 [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) 作業。

## <a name="the-no-cloning-theorem"></a>無複製定理

量子資訊功能強大。
這讓我們能夠執行令人驚奇的事，像是以指數方式比最佳的傳統演算法更快，或有效率地模擬傳統方式需要指數成本才能正確模擬的相互關聯 electron 系統。
不過，配量運算的功能有一些限制。
其中一項限制是由*無複製定理*所提供。

未複製的定理是名為的恰如其。
它不允許由量子電腦複製一般量子狀態。
定理證明十分簡單。
雖然不復制定理的完整證明在這裡的討論方面有點技術性，但在我們的範圍內沒有其他輔助 qubits 的證明（輔助 qubits 會在計算期間用於臨時空間，而且可以在 Q # 中輕鬆使用和管理），請參閱[借用的 qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)）。

對於這類的量子電腦，複製作業必須由單一矩陣描述。
我們不允許測量，因為它會損毀我們嘗試要複製的量子狀態。
為了模擬複製作業，我們想要使用單一矩陣來擁有 $ $ U \ket { \psi } \ket{0 } = \ket { \psi } \ket { \psi 的屬性。}
任何 state $ \ket \psi $ 的 $ $ { } 。
矩陣乘法的線性屬性會暗示任何第二個配量狀態 $ \ket { \phi } $，

$ $ \begin{align}
    U \left [\frac{1 } {\sqrt{2 } } \left （\ket { \phi } + \ket { \psi } \right） \right] \ket{0}
    & = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}
      + \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left （\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}
        \right） \\ \\ & \ne \left （\frac{1 } {\sqrt{2 } } \left （\ket { \phi } + \ket { \psi \right } ） \right） \otimes \left （\frac{1 } {\sqrt{2 } } \left （\ket { \phi } + \ket { \psi } \right） \right）。
\end{align}
$$

這提供了不復制定理背後的基礎直覺：任何複製不明量子狀態的裝置，都必須在其複製的至少部分狀態中引發錯誤。
雖然在輸入狀態上以線性方式執行 cloner 的主要假設是透過新增和測量輔助 qubits 來違反，這類互動也會透過測量統計資料來流失系統的相關資訊，並避免在這種情況下進行完全複製。
如需更完整的無複製定理證明，請參閱[以取得詳細資訊](xref:microsoft.quantum.more-information)。

無複製定理對於區分量子運算而言非常重要，因為如果您可以在較低的情況中複製配量狀態，則會被授與從配量狀態學習的近乎神奇功能。
事實上，您可能違反了海森堡的 vaunted 不確定性原則。
或者，您可以使用最佳的 cloner 從複雜的配量散發取得單一範例，並瞭解您可能會從一個範例中瞭解該散發的所有資訊。
這就像是您翻轉一硬幣和觀察列印頭，然後告訴朋友有關結果的回應「，該硬幣的散佈必須以 $p = 0.512643 \ ldots $ ！」  這類語句不會 sensical，因為有一小部分的資訊（列印頭結果）無法提供編碼散發所需的許多資訊，而不需要大量的先前資訊。
同樣地，如果沒有先前的資訊，我們就無法完全複製量子狀態，因為我們無法準備集團這類的硬幣，而不需要知道 $p $ 。

在量子運算中，資訊不是免費的。
每個 qubit 都有提供一項資訊，而不復制定理顯示沒有任何後門可被利用，來解決系統與在其上叫用之騒之間的基本取捨。
