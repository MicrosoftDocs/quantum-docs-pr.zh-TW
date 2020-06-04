---
title: 量子運算詞彙
description: 用於量子運算的常見詞彙、動作和物件的詞彙。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: 042e4e27ef4e42cfc0c24fbb0ae2232cf1bbfe36
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327606"
---
# <a name="quantum-computing-glossary"></a>量子運算詞彙

## <a name="adjoint"></a>Adjoint

[運算](xref:microsoft.quantum.glossary#operation)的複雜共軛轉置。 針對實作為[單一](xref:microsoft.quantum.glossary#unitary-operator)運算子的作業，adjoint 是運算的反向，並以 dagger 符號表示。 例如，如果作業 `U` 表示 $U $ 的單一運算子，則 `Adjoint U` 表示 $U ^ \dagger $。 如需詳細資訊，請參閱[Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。

## <a name="ancilla"></a>Ancilla

一種[qubit](xref:microsoft.quantum.glossary#qubit) ，可作為量子電腦的暫存記憶體，並視需要配置和解除配置。  如需詳細資訊，請參閱[多個 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。

## <a name="bell-state"></a>鐘州

兩個 qubits 的四個特定最常[光子](xref:microsoft.quantum.glossary#entanglement)配量[狀態](xref:microsoft.quantum.glossary#quantum-state)之一。 四個狀態會定義 $ \ket{\ Beta_ {ij}} = （\mathbb{I} \otimes X ^ iZ ^ j）（\ket {00} + \ket {11} ）/\sqrt {2} $。 鐘狀態也稱為[EPR 配對](xref:microsoft.quantum.glossary#epr-pair)。

## <a name="bloch-sphere"></a>Bloch 球體

單一[qubit](xref:microsoft.quantum.glossary#qubit) [量子狀態](xref:microsoft.quantum.glossary#quantum-state)的圖形表示，做為三維單位球體中的點。 如需詳細資訊，請參閱[使用 Bloch 球體視覺化 Qubits 和轉換](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)。

## <a name="callable"></a>多次

Q # 語言[中的作業或](xref:microsoft.quantum.glossary#operation)[函數](xref:microsoft.quantum.glossary#function)。 如需詳細資訊，請參閱[作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="clifford-group"></a>Clifford 群組

這組作業會佔用[Bloch 球體](xref:microsoft.quantum.glossary#bloch-sphere)的 octants，以及[Pauli 運算子](xref:microsoft.quantum.glossary#pauli-operators)的效果排列。 其中包括作業[$X $](xref:microsoft.quantum.intrinsic.x)、 [$Y $](xref:microsoft.quantum.intrinsic.y)、 [$Z $](xref:microsoft.quantum.intrinsic.z)、 [$H $](xref:microsoft.quantum.intrinsic.h)和[$S $](xref:microsoft.quantum.intrinsic.s)。

## <a name="controlled"></a>管理

接受一或多個[qubits](xref:microsoft.quantum.glossary#qubit)做為目標[作業的啟用程式的量子作業](xref:microsoft.quantum.glossary#operation)。 如需詳細資訊，請參閱[控制和 adjoint 作業](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)。

## <a name="dirac-notation"></a>Dirac 標記法

符號速記，可簡化[量子狀態](xref:microsoft.quantum.glossary#quantum-state)的標記法，亦稱為*bra-ket* notation。  *Bra*部分代表一個資料列向量，例如 $ \bra{A} = \begin{bmatrix} a {_1} & {_2} \end{bmatrix} $，而*ket*部分代表一個資料行向量，$ \ket{B} = \begin{bmatrix} B {_1} \\ \\ B {_2} \end{bmatrix} $。 如需詳細資訊，請參閱[Dirac 標記法](xref:microsoft.quantum.concepts.dirac)。

## <a name="eigenvalue"></a>Eigenvalue

轉換的應用程式變更指定轉換的[eigenvector](xref:microsoft.quantum.glossary#eigenvector)大小的因數。  假設有一個 $M $ 和一個 eigenvector $v $ 的正方形矩陣，然後 $Mv = cv $，其中 $c $ 是 eigenvalue，而且可以是任何引數的複數。 如需詳細資訊，請參閱[Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="eigenvector"></a>Eigenvector

向量，其方向不會由指定的轉換變更，且其大小會由對應于該向量之[eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)的因數來改變。 假設有一個 $M $ 和一個 eigenvalue $c $ 的正方形矩陣，然後 $Mv = cv $，其中 $v $ 是矩陣的 eigenvector，而且可以是任何引數的複數。 如需詳細資訊，請參閱[Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="entanglement"></a>糾纏

配量粒子（例如[qubits](xref:microsoft.quantum.glossary#qubit)）可以連接或*光子*，使其無法彼此獨立地進行描述。 它們的測量結果會相互關聯，即使它們的距離是無限的。 會任何牽連是[測量](xref:microsoft.quantum.glossary#measurement)qubit[狀態](xref:microsoft.quantum.glossary#quantum-state)時不可或缺的。  如需詳細資訊，請參閱[Advanced matrix 概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="epr-pair"></a>EPR 配對

兩個[qubits](xref:microsoft.quantum.glossary#qubit)的四個特定最常光子配量[狀態](xref:microsoft.quantum.glossary#quantum-state)之一。 四個狀態會定義 $ \ket{\ Beta_ {ij}} = （\mathbb {1} \Otimes X ^ iZ ^ j）（\ket {00} + \ket {11} ）/\sqrt {2} $。 EPR 配對也稱為「[鐘」狀態](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>改革

[量子狀態](xref:microsoft.quantum.glossary#quantum-state)隨著時間變更的方式。 如需詳細資訊，請參閱[矩陣指數](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)。

## <a name="function"></a>函式
Q # 語言中純粹為傳統（非配量）的副程式類型。 雖然在配量演算法中使用函式，但它們無法對[qubits](xref:microsoft.quantum.glossary#qubit)或呼叫[作業](xref:microsoft.quantum.glossary#operation)採取動作。 如需詳細資訊，請參閱[作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="gate"></a>蓋

適用[于量子作業](xref:microsoft.quantum.glossary#operation)的舊版詞彙，以傳統邏輯閘道的概念為基礎。 配量[線路](xref:microsoft.quantum.glossary#quantum-circuit-diagram)是閘道（或作業）的網路，以傳統邏輯電路的類似概念為基礎。

## <a name="global-phase"></a>全域階段

當兩個[狀態](xref:microsoft.quantum.glossary#quantum-state)的最大值與 $e ^ {i\phi} $ 的複數多個相同時，就會被視為不同于全域階段。 與本機階段不同的是，全域階段無法透過任何[測量](xref:microsoft.quantum.glossary#measurement)觀察到。 如需詳細資訊，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="hadamard"></a>Hadamard

Hadamard 作業（也稱為 Hadamard 閘道或轉換）會在單一[qubit](xref:microsoft.quantum.glossary#qubit)上運作，並將它放在 $ \ket $ 或 $ \ket $ 的偶數[重迭](xref:microsoft.quantum.glossary#superposition)中（ {0} {1} 如果 qubit 一開始是在 $ \ket {0} $ 狀態中）。 在 Q # 中，這項作業是由預先定義的作業所套用 [`H`](xref:microsoft.quantum.intrinsic.h) 。

## <a name="immutable"></a>固定

無法變更其值的變數。 Q # 中的不可變變數是使用關鍵字所建立 `let` 。 若要宣告*可以*變更的變數，請使用[mutable](xref:microsoft.quantum.glossary#immutable)關鍵字來宣告和 `set` 關鍵字，以修改值。 

## <a name="measurement"></a>測量

[Qubit](xref:microsoft.quantum.glossary#qubit) （或一組 qubits）的操作，其會產生觀察結果，實際上是取得古典位。 如需詳細資訊，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)。

## <a name="mutable"></a>可變動

其值在建立之後可能會變更的變數。 Q # 中的可變變數是使用關鍵字來宣告 `mutable` ，並使用關鍵字進行修改 `set` 。 使用關鍵字建立的變數 `let` 是[不可變](xref:microsoft.quantum.glossary#immutable)的，而且無法變更其值。

## <a name="namespace"></a>命名空間

相關名稱集合的標籤（亦即[作業](xref:microsoft.quantum.glossary#operation) [、函式和](xref:microsoft.quantum.glossary#function)[使用者定義類型](xref:microsoft.quantum.glossary#user-defined-type)）。 例如，命名空間 [ [Microsoft 量子. 準備](xref:microsoft.quantum.preparation)標籤] 會標示標準程式庫中定義的所有符號，以協助準備初始狀態。

## <a name="operation"></a>操作

Q # 中的基本量子執行單位。 它大致等同于 C、c + + 或 Python 中的函式，或是 c # 或 JAVA 中的靜態方法。 如需詳細資訊，請參閱[作業和函數](xref:microsoft.quantum.guide.operationsfunctions)。

## <a name="operator-application"></a>操作員應用程式

執行量子作業。 這通常會將單一矩陣套用至目前的量子狀態向量。

## <a name="oracle"></a>Oracle

副程式，在執行時間提供資料相依的資訊給量子演算法。 一般來說，其目標是要提供對應于重迭中輸入的輸出[重迭](xref:microsoft.quantum.glossary#superposition)。 如需詳細資訊，請參閱[Oracles](xref:microsoft.quantum.libraries.data-structures#oracles)。

## <a name="partial-application"></a>部分應用程式

呼叫[沒有所有](xref:microsoft.quantum.glossary#operation)必要[輸入的函式或作業](xref:microsoft.quantum.glossary#function)。 這會[傳回新的可呼叫](xref:microsoft.quantum.glossary#callable)，其只需要在未來的應用程式期間提供遺漏的參數（以底線表示）。 例如，假設函式可以 `MyFunc(x : int, y : int) : int {return x + y;}` 部分套用至新的函式 `let NewFunc = MyFunc(_, 3)` 。 然後，您可以在稍後使用遺漏參數來呼叫新的函式，傳回 `NewFunc(2)` 值*5*。  如需詳細資訊，請參閱[部分應用程式](xref:microsoft.quantum.guide.operationsfunctions#partial-application)。

## <a name="pauli-operators"></a>Pauli 運算子

一組三個 2 x 2 個單一矩陣，稱為 `X` `Y` 和 `Z` 量子作業。 識別矩陣（$I $）通常也會包含在集合中。  $I = \begin{bmatrix} 1 & 0 \\ \\ 0 & 1 \end{bmatrix} $，$X = \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{bmatrix} $，$Y = \begin{bmatrix} 0 &-i \\ \\ i & 0 \end{bmatrix} $，$Z = \begin{bmatrix} 1 & 0 \\ \\ 0 &-1 \end{bmatrix} $。   如需詳細資訊，請參閱[單一 qubit 作業](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。

## <a name="quantum-circuit-diagram"></a>量子線路圖

以圖形方式表示簡單量副程式之[作業](xref:microsoft.quantum.glossary#operation)（或網[關](xref:microsoft.quantum.glossary#gate)）順序的方法，例如 

![範例電路圖表](~/media/qpe.png). 

如需詳細資訊，請參閱[量子線路](xref:microsoft.quantum.concepts.circuits)。

## <a name="quantum-libraries"></a>量子程式庫

用於建立 Q # 程式的[作業](xref:microsoft.quantum.glossary#operation) [、函](xref:microsoft.quantum.glossary#function)式和[使用者定義類型](xref:microsoft.quantum.glossary#user-defined-type)集合。 預設會安裝[標準程式庫](xref:microsoft.quantum.libraries.standard.intro)。 其他可用的程式庫包括[化學程式庫](xref:microsoft.quantum.chemistry.concepts.intro)、[數值](xref:microsoft.quantum.numerics.intro)程式庫和[機器學習程式庫](xref:microsoft.quantum.machine-learning.concepts.intro)。

## <a name="quantum-state"></a>量子狀態

隔離的量子系統的精確狀態，可從中解壓縮[測量](xref:microsoft.quantum.glossary#measurement)機率。 在量子運算中，配量模擬器會使用這項資訊來模擬 qubits 如何回應作業。 如需詳細資訊，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="qubit"></a>Qubit

一種基本的量子資訊單位，類似于傳統計算中的*一點*。 如需詳細資訊，請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="repeat-until-success"></a>重複直到-成功

機率成功的量子演算法。 失敗時，常式會重試直到成功為止（或已達到限制）。 如需詳細資訊，請參閱[重複直到成功（ru）](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>標準程式庫

在安裝期間，與 Q # 編譯器一起安裝的[作業](xref:microsoft.quantum.glossary#operation) [、函](xref:microsoft.quantum.glossary#function)式和[使用者定義類型](xref:microsoft.quantum.glossary#user-defined-type)。 標準程式庫的執行與目的電腦無關。 如需詳細資訊，請參閱[標準程式庫](xref:microsoft.quantum.libraries.standard.intro)。

## <a name="superposition"></a>重迭

量子計算中的概念是， [qubit](xref:microsoft.quantum.glossary#qubit)是兩個狀態的線性組合，$ \ket {0} $ 和 $ \ket {1} $，直到[測量](xref:microsoft.quantum.glossary#measurement)為止。  如需詳細資訊，請參閱瞭解配量[計算](xref:microsoft.quantum.overview.understanding)。

## <a name="target-machine"></a>目的電腦

將抽象的量副程式降低到硬體或模擬的編譯目標。 這通常包括重新寫入的許多用途，包括閘道更換、錯誤更正的編碼、幾何版面配置等等。 如需詳細資訊，請參閱[量子模擬器和主機應用程式](xref:microsoft.quantum.machines)。

## <a name="teleportation"></a>遙傳

一種方法，可使用[會任何牽連](xref:microsoft.quantum.glossary#entanglement)和[測量](xref:microsoft.quantum.glossary#measurement)，將一個[qubit](xref:microsoft.quantum.glossary#qubit)的資料（或[量子狀態](xref:microsoft.quantum.glossary#quantum-state)）從一個位置重新產生至另一個位置，而不需要實際移動 qubit。  如需詳細資訊，請參閱[量子線路](xref:microsoft.quantum.concepts.circuits)和各 Kata 的[Katas](xref:microsoft.quantum.overview.katas)。

## <a name="tuple"></a>Tuple

以逗號分隔的值集合，可作為單一值。 元組的*類型*是由它所包含的數值型別所定義。 在 Q # 中，元組是[不可變](xref:microsoft.quantum.glossary#immutable)的，而且可以嵌套、包含陣列，或用於陣列中。 如需詳細資訊，請參閱[元組類型](xref:microsoft.quantum.guide.types#tuple-types)。

## <a name="unitary-operator"></a>單一運算子

其反向等於其[adjoint](xref:microsoft.quantum.glossary#adjoint)的運算子，亦即 $UU ^ {\dagger} = \id $。

## <a name="user-defined-type"></a>使用者定義型別

內建或先前定義之類型的集合，可能稱為單一單位。 如需詳細資訊，請參閱[使用者定義類型](xref:microsoft.quantum.guide.types#user-defined-types)。