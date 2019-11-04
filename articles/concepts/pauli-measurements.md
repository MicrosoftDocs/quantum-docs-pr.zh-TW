---
title: Pauli 測量標準 |Microsoft Docs
description: Pauli 測量
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183704"
---
# <a name="pauli-measurements"></a>Pauli 測量

在先前的討論中，我們著重于計算基礎測量。  事實上，從標記的角度來看，在計量運算中所發生的其他常見測量，在計算基礎測量方面很方便表達。  這些測量最常見的一組是*Pauli 測量*。  在這種情況下，通常會討論測量 Pauli 運算子，通常是 $X、Y、Z $ 或 $Z \otimes Z、X\otimes X、X\otimes Y $ 等等的運算子。  討論 Pauli 運算子方面的測量，特別是在量子錯誤更正的子欄位中。 在 Q # 中，我們遵循類似的慣例;我們現在會說明這種替代的度量觀點。

在探究到如何思考 Pauli 測量的詳細資料之前，請考慮測量量子電腦內的單一 qubit 對量子狀態的作用。  假設我們有一個 $n $-qubit 量子狀態;然後，測量一個 qubit 會立即將該狀態所可能處於 $ 2 ^ n $ 可能性的一半。  換句話說，測量會將量子狀態投射到兩個半形的其中一個。  我們可以將我們認為測量的方式一般化，以反映這種情況。

為了簡潔地識別這些 subspaces，我們需要用來描述它們的語言。  執行這項操作的方法之一，是透過僅具有兩個唯一特徵值的矩陣來指定兩個 subspaces，慣例是 $ \pm $1。  最簡單的範例是：

$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}。
$$

$Z Pauli $ 矩陣清楚地有兩個特徵向量 $ \ket{0}$ 和 $ \ket{1}$ with 特徵值 $ \pm $1。  因此，如果我們測量 qubit，並取得 $ \ket{0}$ 我們在 $ + $1 eigenspace 中（所有向量的集合，其組成的特徵向量總和只有正值或唯一的負特徵值），而且如果我們測量 $ \ket{1}$，我們是在 $-$1 ei 中$Z $ 的 genspace。  此程式在 Pauli 測量的語言中稱為「測量 Pauli $Z $」，完全等同于執行計算基礎測量。

當然，任何 $ 2 \ 1 倍的 $2 矩陣，都是 $Z $ 的單一轉換，也符合此準則。  這表示我們也可以考慮將矩陣 $A = U ^ \dagger Z U $ （針對任何單一矩陣 $U $）提供一個矩陣，在其 $ \pm $1 特徵向量中定義度量的兩個結果。  Pauli 量值的標記法會藉由將 $X、Y、Z $ 測量值識別為對等的測量，以取得 qubit 中的資訊。  為了方便起見，以下提供這些測量。

$ $ \begin{array}{| c | c |} \text{Pauli 量測} & U\\\\ Z & \boldone\\\\ X & H\\\\ Y & HS ^ \dagger\\\\ \end{array} $ $

也就是說，使用這種語言，「量值 $Y $」等同于套用 $HS ^ \dagger $，然後以計算為基礎來測量，其中 $S $ 是所謂的階段閘道，由

$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}。
$$

這也相當於將 $HS ^ \dagger $ 套用至量子狀態向量，然後測量 $Z $。  接著，轉換回計算基礎，即可找到正確的狀態，這是將 $SH $ 套用至量子狀態向量的數量。

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>從量子狀態取得的 Q # 結果傳統資訊
在 Q # 中，我們假設結果（也就是從與狀態互動時所解壓縮的傳統資訊）是 $j $ （如果是在 Pauli 運算子的 $ （-1） ^ j $ eigenspace 中），而這是在設定 $\{0，1\}$ 中。

多 qubit Pauli 運算子的度量定義類似，如下所示：

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ end {bmatrix}。
$$

因此，兩個 Pauli $Z $ 運算子的張量產品會形成一個矩陣，其中包含由 $ + $1 和 $-$1 特徵值組成的兩個空格。  就像單一 qubit 的情況一樣，兩者都構成一半空間，這表示可存取的兩個向量空間一半屬於 $ + $1 eigenspace，而其餘一半則是 $-$1 eigenspace。  一般來說，您可以從張量產品的定義中查看 Pauli-$Z $ operators 的任何張量產品，以及身分識別也會遵守這項功能。  例如，

$ $ Z\otimes\boldone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ end {bmatrix}。
$$

如前所述，這類矩陣的任何單一轉換也會描述由 $ \pm $1 特徵值標記的兩個半形。  例如，從 $Z = HXH $ 的身分識別 $X \otimes X = H\otimes H （Z\otimes Z） H\otimes H $。  與一個 qubit 的案例類似，所有的雙 qubit Pauli 量值都可以撰寫為 $U ^ \dagger （Z\otimes \id） U $ （適用于 $ 4 \ 次 $4 單一矩陣 $U $）。  我們會列舉下表中的轉換，為方便起見，交換閘道會交換 qubits $0 $ 和 $1 $： $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{CNOT-CONTAINS}\_{01}$：

$ $ \begin{array}{| c | c |} \text{Pauli 測量} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone & HS ^ \dagger\otimes \boldone\\\\ \boldone \otimes Z & \operatorname{SWAP}\\\\ \boldone \otimes X & （H\otimes \boldone） \operatorname{SWAP}\\\\ \boldone \otimes Y & （HS ^ \dagger\otimes \boldone） \運算子名稱 {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}（H\otimes \boldone）\\\\ Y\otimes Z & \運算子名稱 {CNOT-CONTAINS}\_{10}（HS ^ \dagger\otimes \boldone）\\\\ Z\otimes X & \operatorname{CNOT}\_{10}（\boldone\otimes H）\\\\ X\otimes X & \operatorname{CNOT}\_{10}（H\otimes H）\\\\ Y\otimes X & \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes H）\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}（\boldone \otimes HS ^ \dagger）\\\\ X\otimes Y & \operatorname{CNOT}\_{10}（H\otimes HS ^ \dagger）\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}（HS ^ \dagger\otimes HS ^ \dagger）\\\\ \end{array} $ $

這裡會出現閘道 $ \operatorname{CNOT}\_{10}$，原因如下。  不包含 $ \boldone $ 矩陣的每個 Pauli 量值，都相當於單一的，以由上述推理 $Z \otimes Z $。  $Z \otimes Z $ 的特徵值僅取決於組成每個計算基礎向量的 qubits 同位檢查，而此清單中所顯示的受控制-非作業則是用來計算此同位，並將其儲存在第一位。  然後在測量第一個位之後，我們就可以復原所產生的半空間識別，這相當於測量 Pauli 運算子。

另外還有一點要注意的是，假設測量 $Z \otimes Z $ 的量值與測量 $Z \otimes \id $ 和 $ \id \otimes Z $ 相同，這項假設會是 false。  原因是測量 $Z \otimes Z $ 將量子狀態投射到這些運算子的 $ + $1 或 $-$1 eigenstate 中。  測量 $Z \otimes \id $ 然後 $ \id \otimes Z $ 會先將量子狀態向量投射到 $Z \otimes \id $ 的一半空間，然後再到 $ \id \otimes Z $ 的半形。  因為有四個計算基礎的向量，同時執行這兩個度量會將狀態縮減為四分之一空間，因而減少為單一計算基礎向量。


## <a name="correlations-between-qubits"></a>Qubits 之間的相互關聯
另一個查看 Paulis 張量產品（例如 $X \otimes X $ 或 $Z \otimes Z $）的方法，就是這些測量可讓您查看儲存在兩個 qubits 之間關聯性的資訊。  測量 $X \otimes \id $，可讓您查看本機儲存在第一個 qubit 中的資訊。  雖然這兩種類型的測量在量子運算中也同樣有價值，但前者也會照亮量子運算的威力。 它會發現，在量子運算中，您想要學習的資訊通常不會儲存在任何單一 qubit 中，而是會一次儲存在所有 qubits 中，而只是透過搭配 $Z \otimes Z $ 的結合測量來進行，這項資訊會變成清單.

您也可以測量任意的 Pauli 運算子，例如 $X \otimes Y \otimes Z \otimes \boldone $。  Pauli 運算子的所有這類張量產品只有兩個特徵值 $ \pm $1，而這兩個 eigenspaces 構成整個向量空間的半個空格。  因此，它們會符合上面所述的需求。

在 Q # 中，這類測量結果會在 eigenspace 中產生正負號 $ （-1） ^ j $ 的值時，傳回 $j $。  將此項當做 Q # 內建功能很有説明，因為測量這類運算子時，需要長鏈的受控制（而非閘道和基礎轉換）來描述將作業當做 $Z $ 和 $ \id $ 的張量產品來表達作業所需的 diagonalizing $U $ 閘道。  只要能夠指定您想要執行其中一項預先定義的測量，就不需要擔心如何轉換基礎，讓計算基礎測量提供必要的資訊。  問 # 會自動為您處理所有必要的基礎轉換。 請參閱[Pauli 測量的 Q # 程式庫參考](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>無複製定理
量子資訊功能強大。  這讓我們能夠執行令人驚奇的事，像是以指數方式比最佳的傳統演算法更快，或有效率地模擬傳統方式需要指數成本才能正確模擬的相互關聯 electron 系統。  不過，配量運算的功能有一些限制。  其中一項限制是由*無複製定理*所提供。

未複製的定理是名為的恰如其。
它不允許由量子電腦複製一般量子狀態。
定理證明十分簡單。
雖然不復制定理的完整證明在本文的討論方面有點技術性，但在有問題的量子電腦沒有其他 ancilla qubits 的情況下，定理的證明也在我們的範圍內（ancilla qubits 是用於全新 qubits計算期間的空間，並可在 Q # 中輕鬆使用和管理，請參閱 <xref:microsoft.quantum.techniques.qubits>）。
對於這類的量子電腦，複製作業必須是單一矩陣。 我們不允許測量，因為它會損毀我們嘗試要複製的量子狀態。 我們想要的單一矩陣必須有 $ $ U \ket{\psi} \ket 的屬性，{0} = \ket{\psi} \ket{\psi}，$ $ 適用于任何 state $ \ket{\psi} $。
矩陣乘法的線性屬性會暗示任何第二個配量狀態 $ \ket{\phi} $，

\begin{align} & U\left [\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ phi} \ ket{0}+ \frac{1}{\sqrt{2}} U\ket {\ psi} \ ket{0}\\\\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left （\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right）\\\\ & \qquad\qquad\ne \left （\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right） \otimes\left （\frac{1}{\sqrt{2}} \left （\ket{\phi} + \ket{\psi} \right） \right）。
\end{align}

這提供了不復制定理背後的基礎直覺：任何複製不明量子狀態的裝置，都必須在其複製的至少部分狀態中引發錯誤。  雖然 cloner 的關鍵假設是透過新增 ancilla qubits 的 ancilla 和測量，因而違反了輸入狀態，但這類互動也會透過測量統計資料來流失系統的相關資訊，並防止在這種情況下也會進行精確的複製。  如需更完整的無複製定理證明，請參閱[以取得詳細資訊](xref:microsoft.quantum.more-information)。

無複製定理對於區分量子運算而言非常重要，因為如果您可以在較低的情況中複製配量狀態，則會被授與從配量狀態學習的近乎神奇功能。  事實上，您可能違反了海森堡的 vaunted 不確定性原則。  或者，您可以使用最佳的 cloner 從複雜的配量散發取得單一範例，並瞭解您可能會從一個範例中瞭解該散發的所有資訊。  這就像是您翻轉一硬幣和觀察列印頭，然後告訴朋友有關結果的回應「，該硬幣的散佈必須以 $p = 0.512643 \ ldots $！  這類語句不會 sensical，因為有一小部分的資訊（列印頭結果）無法提供編碼散發所需的許多資訊，而不需要大量的先前資訊。  同樣地，如果沒有先前的資訊，我們就無法完全複製配量狀態，因為我們無法準備集團這類的硬幣，而不需要知道 $p $。

在量子運算中，資訊不是免費的。  每個 qubit 都有提供一項資訊，而不復制定理顯示沒有任何後門可被利用，來解決系統與在其上叫用之騒之間的基本取捨。

