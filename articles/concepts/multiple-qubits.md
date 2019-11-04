---
title: 多個 qubits |Microsoft Docs
description: 多個 qubits
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3e0404cfd67f693ff6b7a8297566e59208fc7ec0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183772"
---
# <a name="multiple-qubits"></a>多個 Qubits

雖然單一 qubit 閘道具有一些非常直覺的功能，例如能夠在指定時間處於一個以上的狀態，但如果您在量子電腦中只有單一 qubit 的閘道，則會有一個裝置具有可小巫見大巫的計算能力即使是計算機也可以單獨使用傳統超級電腦。
只有當我們增加 qubits 數目時，才會明顯地看到量子運算的真正威力。
這項功能的發生原因是，配量狀態向量的向量空間維度，會隨著 qubits 的數目以指數方式成長。
這表示，雖然單一 qubit 可以完整模型化，但是模擬 50 qubit 的量子計算可能會推送現有超級電腦的限制。
只有一個額外的 qubit 會增加計算的大小，這會使儲存狀態所需的記憶體*加倍*，而且大約是計算時間*加倍*。
這倍的運算能力很快就是為什麼配量電腦的 qubits 數量相對較少，在某些計算工作中的超級電腦最強大。

為什麼會有量子狀態向量的指數成長？  本節的目標是要探討用來建立多 qubit 狀態的規則，而不是單一 qubit 的狀態，以及討論我們需要在閘道集中包含的閘道作業，以構成通用的多 qubit 量子電腦。
這些工具絕對需要用來瞭解問 # 程式碼中常用的閘道集，也可以取得直覺的原因，例如會任何牽連或干擾轉譯配量計算比傳統運算更強大。

## <a name="representing-two-qubits"></a>代表兩個 Qubits
一到兩個 qubit 狀態的主要差異在於兩個 qubit 的狀態是四維，而不是二維。
這是因為兩個 qubit 狀態的計算基礎是由一 qubit 狀態的張量產品所組成。  例如，我們有 \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}、\qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}、\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}、\qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}。
\end{align}

很容易看到，$n $ qubits 的配量狀態通常是以維度 $ 2 ^ n $ 的單位向量表示，並使用此結構。  向量

$ $ \begin{bmatrix} \ Alpha_{00} \\\\ \ Alpha_{01} \\\\ \ Alpha_{10} \\\\ \ Alpha_{11} \end{bmatrix} $ $

代表兩個 qubits 的配量狀態（如果 $ | \ Alpha_{00}| ^ 2 + | \ Alpha_{01}| ^ 2 + | \ Alpha_{10}| ^ 2 + | \ Alpha_{11}| ^ 2 = 1 $。 就像單一 qubits，多個 qubits 的量子狀態向量會保存描述系統行為所需的所有資訊。

如果我們提供兩個不同的 qubits，一個在 state $ \begin{bmatrix} \Alpha \\\\ \Beta \end{bmatrix} $，而第二個 qubit 處於 state $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $，對應的雙 qubit 狀態為

$ $ \begin{bmatrix} \Alpha \\\\ \Beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \Alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \搶鮮版（Beta） \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \Alpha\gamma \\\\ \Alpha\delta \\\\ \Beta\gamma \\\\ \Beta\delta \end{bmatrix}，$ $

其中，$ \otimes $ 的作業稱為向量的張量產品（或 Kronecker 產品）。 請注意，雖然我們一定可以讓兩個單一 qubit 狀態的張量產品形成兩個 qubit 的狀態，而不是所有的兩 qubit 配量狀態都可以撰寫為兩個單一張量狀態的 qubit 產品。
例如，沒有州 $ \psi = \begin{bmatrix} \Alpha \\\\ \Beta \end{bmatrix} $ 和 $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $，使其張量產品為狀態 

$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

這種 qubit 狀態無法寫入為單一 qubit 狀態的張量產品，稱為「光子狀態」;這兩個 qubits 稱為[*光子*](https://en.wikipedia.org/wiki/Quantum_entanglement)。  鬆散說，因為無法將配量狀態視為單一 qubit 狀態的張量產品，所以狀態所保存的資訊不會個別限制為任何 qubits。  而是在這兩個狀態之間的相互關聯中，以非本機方式儲存資訊。  這種非位置的資訊是傳統運算上的量子運算的其中一項主要區別功能，對於一些量子通訊協定（包括[量子 teleportation](https://github.com/Microsoft/Quantum/tree/master/Samples/src/Teleportation)和[量子錯誤更正](xref:microsoft.quantum.libraries.error-correction)）而言，這是很重要的。

## <a name="measuring-two-qubit-states"></a>測量兩個 Qubit 的狀態 ##
測量兩個 qubit 的狀態與單一 qubit 測量非常類似。 測量狀態

$ $ \begin{bmatrix} \ Alpha_{00} \\\\ \ Alpha_{01} \\\\ \ Alpha_{10} \\\\ \ Alpha_{11} \end{bmatrix} $ $

產生 $0 $，機率為 $ | \ Alpha_{00}| ^ $2，$1 $ 具有機率 $ | \ Alpha_{01}| ^ $2，$10 $，機率為 $ | \ Alpha_{10}| ^ $2，而 $11 $ 具有機率 $ | \ Alpha_{11}| ^ $2。 變數 $ \ Alpha_{00}，\ Alpha_{01}，\ Alpha_{10}，$ 和 $ \ Alpha_{11}$ 已刻意命名，以讓此連接清楚。 測量之後，如果結果為 $0 $，則兩個 qubit 系統的配量狀態會折迭，現在是

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}。
$$

您也可以只測量兩個 qubit 量子狀態的一個 qubit。 在只測量其中一個 qubits 的情況下，測量的影響會稍微不同，因為整個狀態不會折迭成計算基礎狀態，而只會折迭到一個子系統。  換句話說，在這種情況下，測量只有一個 qubit 只會折迭其中一個子系統，而不是全部折迭。  

若要瞭解這一點，請考慮測量下列狀態的第一個 qubit，這是透過套用 Hadamard 轉換 $H $ （一開始是設定為 "0" 狀態的兩個 qubits 上所形成）： $ $ H ^ {\otimes 2} \left （\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \right） = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 &t_10_ \\ 1 &-1 &-1 & 1 \end{bmatrix}\begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ end {bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \mapsto \begin{cases}\text{outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\ 1\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \text{outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{案例}。
$ $ 這兩個結果的發生率為50%。  這兩者的結果為50% 機率的 intuited，是因為第一個 qubit 上的初始配量狀態向量在交換 $0 $1 $ 底下不變。

測量第一個或第二個 qubit 的數學規則很簡單。  如果我們讓 $e _k $ 是 $k ^ {\rm th} $ 計算基礎向量，並讓 $S $ 是所有 $e $ 的集合，如此一來，問題的 qubit 就會將該值 _k $ 的值設為 $1 $。  例如，如果我們有興趣測量第一個 qubit，則 $S $ 會包含 $e _2 \ HTTP-equiv $10 和 $e _3 \ HTTP-equiv $11。  同樣地，如果我們對第二個 qubit 有興趣 $S $ 會包含 $e _1 \ HTTP-equiv $1 和 $e _3 \equiv $11。  然後，測量所選 qubit 為 $1 $ 的機率是針對狀態向量 $ \psi $

$ $ P （\text{outcome} = 1） = \ sum_ {e_k 集合中的 \text{} S} \psi ^ \dagger e_k e_k ^ \dagger \psi。
$$

由於每個 qubit 量測只能產生 $0 $ 或 $1 $，測量 $0 $ 的機率只是 $1-P （\text{outcome} = 1） $。  這就是為什麼我們只會針對測量 $1 $ 的機率明確提供公式。

這類測量具有狀態的動作可以數學方式表示為

$ $ \psi \mapsto \frac{\ sum_ {e_k \text{在 set} S} e_k e_k ^ \dagger \psi}{\sqrt{P （\text{outcome} = 1）}}。
$$

謹慎的讀者可能會擔心測量的機率為零時，會發生什麼事。  雖然在此情況下，結果狀態是未定義的，但我們不需要擔心這類 eventualities，因為機率為零！


如果我們將 $ \psi $ 視為上述的統一狀態向量，並有興趣測量第一個 qubit， 

$ $ P （第一個 qubit 的 \text{measurement} = 1） = （\psi ^ \dagger e_2）（e_2 ^ \dagger \psi） + （\psi ^ \dagger e_3）（e_3 ^ \dagger \psi） = | e_2 ^ \dagger \psi | ^ 2。
$$

請注意，這只是測量結果 $10 $ 和 $11 $ 所預期的兩個機率的總和，全都是要測量的 qubits。
在我們的範例中，這會評估為

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ 結束 {bmatrix} \ begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \開始 {bmatrix} 0 & 0 & 0 & 1 \ end {bmatrix} \ begin {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ end {bmatrix} \right | ^ 2 = \frac{1}{2}。
$$

這完全符合我們的直覺告訴我們機率的可能性。  同樣地，狀態可以寫成

$ $ \frac{\frac{e_2}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ end {bmatrix} $ $

再次遵循我們的直覺。

## <a name="two-qubit-operations"></a>兩個 Qubit 的作業
就像在單一 qubit 的情況下，任何單一轉換都是 qubits 上的有效操作。 一般來說，在 $n $ qubits 上的單一轉換是一個大小為 $ 2 ^ n \times 2 ^ n $ 的 $U 矩陣（因此它會作用於大小為 $ 2 ^ n $ 的向量），因此 $U ^{-1} = U ^ \dagger $。 例如，CNOT-CONTAINS （受控制-NOT）閘道是常用的兩個 qubit 閘道，由下列單一矩陣表示：

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \end{bmatrix} $ $

我們也可以在兩個 qubits 上套用單一 qubit 閘道來形成兩個 qubit 的閘道。 例如，如果我們套用閘道 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

與

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

對於第一個和第二個 qubits，這相當於套用張量\\產品所指定的兩個 qubit，\\ c-d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin {bmatrix} ae \ qubit \ bf \\\\ ag \ 張量 \\\\ ce \ cf \ de \ df \\\\ cg \ ch \ dg \ dh \end{bmatrix}. $ $，因此我們可以藉由採用一些已知單一 qubit 閘道的產品來形成兩個的閘道。 兩個 qubit 閘道的一些範例包括 $H \otimes H $、$X \otimes \boldone $ 和 $X \otimes Z $。

請注意，雖然任何兩個單一 qubit 閘道都是藉由接受張量產品來定義雙 qubit 閘道，相反的情況也不是如此。 並非所有的兩個 qubit 閘道都可以撰寫成單一 qubit 閘道的張量產品。  這種閘道稱為*entangling*閘道。 Entangling 閘道的其中一個範例是 CNOT-CONTAINS 閘道。

受控制-not 閘道後方的直覺可以一般化至任意閘道。  受控制的閘道通常是做為身分識別的閘道（即沒有動作），除非特定的 qubit 是 $1 $。  我們在標記為 $x $ 的 qubit 上，以 $ \Lambda\_x （U） $ 表示受控制的單一控制項（在此案例中為）。  作為範例 $ \ Lambda_0 （U） e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ 和 $ \Lambda\_0 （U） e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $，其中 $e\_$0 和 $e\_$1 是對應至值 $0 $ 和 $1 $ 之單一 qubit 的計算基礎向量。  例如，請考慮下列受控制的 $Z $ 閘道，然後我們可以將其表示為 $ $ \Lambda\_0 （Z） = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 & 0\\\\0 & 0 & 0 &-1 \end{bmatrix} = （\boldone\otimes H） \operatorname{CNOT} （\boldone\otimes H）。
$$

以有效率的方式建立受控制的 unitaries 是一項重大挑戰。  執行此作業最簡單的方式，就是建立一個受控制版本之基本閘道的資料庫，並將原始單一作業中的每個基本閘道取代為其控制的對應。  這通常很浪費，而且聰明的深入解析通常可用來以控制的版本來取代幾個閘道，以達到相同的影響。  基於這個理由，我們在架構中提供了一種功能，可以執行控制或允許使用者定義受控制版本的單一（如果已知優化的手動調整版本）。

閘道也可以使用傳統資訊來控制。  例如，傳統方式控制的 not 閘道只是一般的 not 閘道，但只有在傳統位是 $1 $ 而不是配量位時，才會套用。  就這一點而言，傳統方式控制的閘道可以視為量副程式代碼中的 if 語句，其中閘道只會在程式碼的一個分支中套用。


如同在單一 qubit 的情況中，如果有任何 $ 4 \ 乘以 $4 單一矩陣，則此集合中的閘道的產品可能會將其近似為任意精確度，這兩個 qubit 閘道集會設定為通用。
通用閘道集的其中一個範例是 Hadamard 閘道、T 閘道和 CNOT-CONTAINS 閘道。 藉由取得這些閘道的產品，我們就可以在兩個 qubits 上大致估計任何單一矩陣。

## <a name="many-qubit-systems"></a>多 Qubit 系統
我們遵循兩個 qubit 案例中所探索到的相同模式，從較小的系統建立多 qubit 的配量狀態。  這種狀態是藉由形成較小狀態的張量產品所建立。  例如，請考慮在量子電腦中編碼位字串 $1011001 $。  我們可以將此編碼為

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}。
$$

量子閘道的工作方式完全相同。  例如，如果我們想要將 $X $ 閘道套用至第一個 qubit，然後在第二個和第三個 qubits 之間執行 CNOT-CONTAINS，我們可以將此轉換表示為

\begin{align} & （X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone） \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001。
\end{align}

在許多 qubit 系統中，通常需要配置和取消配置 qubits，做為量子電腦的暫存記憶體。  這種 qubit 稱為 ancilla。  根據預設，我們假設 qubit 狀態已初始化為在配置時 $e _0 $。  我們會進一步假設在解除配置之前，會再次傳回 $e _0 $。  這項假設很重要，因為如果 ancilla qubit 在解除配置時，與另一個 qubit 暫存器光子，則取消配置的程式將會損毀 ancilla。  基於這個理由，我們一律假設這類 qubits 會在發行之前還原成其初始狀態。

最後，雖然需要將新的閘道新增至閘道，以達到兩個 qubit 量子電腦的通用量子運算，但在多 qubit 的情況下，不需要引進新的閘道。  閘道 $H $、$T $ 和 CNOT-CONTAINS 會形成在許多 qubits 上設定的通用閘道，因為任何一般的單一轉換都可以分成一系列的兩個 qubit 旋轉。  然後，我們可以利用針對兩個 qubit 案例所開發的理論，並在有許多 qubits 時再次使用。

雖然我們目前使用的線性代數標記法可以用來描述多 qubit 的狀態，但是因為我們增加了狀態的大小，所以變得越來越繁瑣。  例如，長度為7位字串的產生的資料行向量為 $128 $ 維，這會使用先前所述的標記法來表示它，這會是非常麻煩的。  基於這個理由，我們接下來會在配量運算中呈現常見的標記法，讓我們能夠簡明扼要地描述這些高維度的向量。
