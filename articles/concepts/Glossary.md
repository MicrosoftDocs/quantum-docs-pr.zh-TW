---
title: 量子計算詞彙表
description: 量子計算中使用的常用術語、操作和物件的詞彙表。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482216"
---
# <a name="quantum-computing-glossary"></a>量子計算詞彙表

## <a name="adjoint"></a>伴隨

操作的複雜共聚[轉換。](xref:microsoft.quantum.glossary#operation) 對於實現[單一](xref:microsoft.quantum.glossary#unitary-operator)運算符的操作,鄰接是操作的反向,由劍符號表示。 例如,如果操作`U`表示單一運算元 $U$,`Adjoint U`則表示 $U\agger$。 有關詳細資訊,請參閱[Ad和](xref:microsoft.quantum.language.file-structure#adjoint)

## <a name="ancilla"></a>安西拉

用作量子電腦的臨時記憶體並根據需要分配和取消分配的[qubit。](xref:microsoft.quantum.glossary#qubit)  有關詳細資訊,請參閱[多個量子位](xref:microsoft.quantum.concepts.multiple-qubits)。

## <a name="bell-state"></a>貝爾州

四個特異性最大[糾纏](xref:microsoft.quantum.glossary#entanglement)[的量子態](xref:microsoft.quantum.glossary#quantum-state)之一,兩個量子位。 這四種狀態定義 $ket_beta_{i}= (\mathbb_I__otimes X_iZ_j){00} (\ket{11}={2}\ket) / \sqrt $。 貝爾狀態也稱為[EPR 對](xref:microsoft.quantum.glossary#epr-pair)。

## <a name="bloch-sphere"></a>布洛赫球體

單[量子位](xref:microsoft.quantum.glossary#qubit)[量子態](xref:microsoft.quantum.glossary#quantum-state)的圖形表示形式,作為三維單元球體的點。 有關詳細資訊,請參閱使用[Bloch 球體視覺化的 Qubit 和變換](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)。

## <a name="callable"></a>呼叫

Q# 語言中的[操作](xref:microsoft.quantum.glossary#operation)或[函數](xref:microsoft.quantum.glossary#function)。 有關詳細資訊,請參閱[操作和函數類型](xref:microsoft.quantum.language.type-model#operation-and-function-types)。

## <a name="clifford-group"></a>克利福德集團

佔據[布洛赫球體的](xref:microsoft.quantum.glossary#bloch-sphere)八進位和[保利運算符](xref:microsoft.quantum.glossary#pauli-operators)的效應排列的一組操作。 其中包括[$X$、$Y$、$Z$、$H](xref:microsoft.quantum.intrinsic.x)[美元](xref:microsoft.quantum.intrinsic.h)和[$S美元](xref:microsoft.quantum.intrinsic.s)。 [$Y$](xref:microsoft.quantum.intrinsic.y) [$Z$](xref:microsoft.quantum.intrinsic.z)

## <a name="controlled"></a>控制

將一個或多個[量子位](xref:microsoft.quantum.glossary#qubit)作為目標操作的啟用器的量子[運算](xref:microsoft.quantum.glossary#operation)。 有關詳細資訊,請參閱[受控](xref:microsoft.quantum.language.type-model#controlled)。

## <a name="dirac-notation"></a>狄拉克符號

簡化[量子態](xref:microsoft.quantum.glossary#quantum-state)表示的符號速記,也稱為*胸帶*符號。  *bra*部分表示行向量,例如 ${bra}A} } [開始]bmatrix} A[1]& A{2}\end_bmatrix_$和*ket*部分表示列向量,${ket{B} \\ \\ = {開始}bmatrix} B{1}B}2}{2}=$$。 有關詳細資訊,請參閱[Dirac 符號](xref:microsoft.quantum.concepts.dirac)。

## <a name="eigenvalue"></a>特徵

給定變換的[eigenvector](xref:microsoft.quantum.glossary#eigenvector)大小因轉換的應用而改變的因數。  給定一個平方矩陣$M$和一個 eigenvector$v$,然後$Mv = cv$,其中$c$是 eigen值,可以是任何參數的複雜數位。 有關詳細資訊,請參閱[進階矩陣概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="eigenvector"></a>艾根向量

方向因給定變換而保持不變,其幅度由對應於該向量的[eigen 值](xref:microsoft.quantum.glossary#eigenvalue)的因數改變的向量。 給定一個平方矩陣$M$和一個 eigenvalue $c$,然後$Mv = cv$,其中$v$是矩陣的 eigenvector,可以是任何參數的複雜數位。 有關詳細資訊,請參閱[進階矩陣概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="entanglement"></a>糾纏

量子粒子,如[量子位](xref:microsoft.quantum.glossary#qubit),可以連接或*糾纏*,以至於它們不能相互獨立地描述。 即使它們相距無限遠,它們的測量結果也是相互關聯的。 糾纏對於[測量](xref:microsoft.quantum.glossary#measurement)量子位[的狀態](xref:microsoft.quantum.glossary#quantum-state)至關重要。  有關詳細資訊,請參閱[進階矩陣概念](xref:microsoft.quantum.concepts.matrix-advanced)。

## <a name="epr-pair"></a>EPR 對

四個特異性最大糾纏[的量子態](xref:microsoft.quantum.glossary#quantum-state)之一,兩[個量子位](xref:microsoft.quantum.glossary#qubit)。 這四{1}種狀態定義 $ket\beta_[ij]= (\mathbb \otimes X_iZ_j){00} {11}(\ket = \ket{2}) / \sqrt $。 EPR 對也稱為[貝爾狀態](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>演化

[量子狀態](xref:microsoft.quantum.glossary#quantum-state)如何隨時間而變化。 有關詳細資訊,請參閱[矩陣指數](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)。

## <a name="function"></a>函式
Q# 語言中純經典(非量子)的子例程類型。 雖然函數在量子演演演算法中使用,但它們不能對[量子位](xref:microsoft.quantum.glossary#qubit)或調用操作執行[操作](xref:microsoft.quantum.glossary#operation)。 有關詳細資訊,請參閱[操作和函數類型](xref:microsoft.quantum.language.type-model#operation-and-function-types)。

## <a name="gate"></a>門

基於經典邏輯門的概念的量子[運算](xref:microsoft.quantum.glossary#operation)的一個遺留術語。 [量子電路](xref:microsoft.quantum.glossary#quantum-circuit-diagram)是基於經典邏輯電路的類似概念的門(或操作)網路。

## <a name="global-phase"></a>全球階段

當兩個[狀態](xref:microsoft.quantum.glossary#quantum-state)與複數$e[i_phi]$的倍數相同時,它們據說在全域階段之前有所不同。 與局部階段不同,全球階段無法通過任何[測量](xref:microsoft.quantum.glossary#measurement)來觀察。 有關詳細資訊,請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="hadamard"></a>Hadamard

Hadamard 操作(也稱為 Hadamard 門或變換)在單個[qubit](xref:microsoft.quantum.glossary#qubit)上操作,如果{0}{0}qubit 最初處於 $ket $ 狀態,{1}則將其置於 $ket $或 $$$ 的均勻[疊加中](xref:microsoft.quantum.glossary#superposition)。 在 Q# 中,此操作由預[`H`](xref:microsoft.quantum.intrinsic.h)先定義的操作應用。

## <a name="immutable"></a>固定

其值無法更改的變數。 使用`let`關鍵字建立 Q# 中的不可變數。 要聲明*可以*更改的變數,請使用[可變](xref:microsoft.quantum.glossary#immutable)關鍵字`set`聲明, 使用關鍵字修改值。 

## <a name="measurement"></a>測量

對產生觀測結果的[量子位](xref:microsoft.quantum.glossary#qubit)(或一組量子位)的操作,實際上獲取經典位。 有關詳細資訊,請參閱[Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)。

## <a name="mutable"></a>可變動

創建其值後可能會更改的變數。 Q# 中的可變數使用`mutable`關鍵字聲明並使用 關鍵`set`字 進行修改。 使用`let`關鍵字創建的變數是不[可變的](xref:microsoft.quantum.glossary#immutable),並且不能更改其值。

## <a name="namespace"></a>命名空間

相關名稱集合(即[操作](xref:microsoft.quantum.glossary#operation)、[函數](xref:microsoft.quantum.glossary#function)和[使用者定義類型)](xref:microsoft.quantum.glossary#user-defined-type)的標籤。 例如,命名空間[Microsoft.Quantum.準備](xref:microsoft.quantum.preparation)標記標準庫中定義的所有符號,以説明準備初始狀態。

## <a name="operation"></a>作業

Q#中量子執行的基本單位。 它大致等效於 C、C++ 或 Python 中的函數,或 C# 或 Java 中的靜態方法。 有關詳細資訊,請參閱[操作和函數類型](xref:microsoft.quantum.language.type-model#operation-and-function-types)。

## <a name="operator-application"></a>操作員應用程式

執行量子運算。 這通常將單一矩陣應用於當前量子狀態向量。

## <a name="oracle"></a>Oracle

在運行時向量子演演演算法提供與數據相關的資訊的子例程。 通常,目標是提供與疊加的輸入對應的輸出[的疊加](xref:microsoft.quantum.glossary#superposition)。 有關詳細資訊,請參閱[Oracle](xref:microsoft.quantum.libraries.data-structures#oracles)。

## <a name="partial-application"></a>部分應用

在沒有所有所需輸入的情況下呼叫[函數](xref:microsoft.quantum.glossary#function)或[操作](xref:microsoft.quantum.glossary#operation)。 這將返回一個新的[可調用,該參數](xref:microsoft.quantum.glossary#callable)只需要在將來的應用程式期間提供缺少的參數(由下劃線指示)。 例如,給定函數`MyFunc(x : int, y : int) : int {return x + y;}`,您可以將其部分應用於新函`let NewFunc = MyFunc(_, 3)`數 。 然後,可以使用返回值`NewFunc(2)`*5*的缺失參數稍後調用新函數。  有關詳細資訊,請參閱[部分應用程式](xref:microsoft.quantum.language.expressions#partial-application)。

## <a name="pauli-operators"></a>保利操作員

一組三個 2 x 2 單`X`一`Y``Z`矩陣, 稱為 和量子運算。 標識矩陣$I$也通常包含在集中。  $I = [開始]bmatrix= \\ \\ 1 & 0 0 & \\ \\ 1 [end_bmatrix]$,$X = [開始]bmatrix] 0 & 1 1 & 0\\\\[結束 ]bmatrix$,$Y = [開始]bmatrix0 & -i & \\ \\ 0 [結束]bmatrix$,$Z = [開始]bmatrix] 1 & 0 & -1 [結束]\bmatrix_$。   有關詳細資訊,請參閱[單量子位操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)。

## <a name="quantum-circuit-diagram"></a>量子電路圖

一種以圖形方式表示簡單量子程式[的操作](xref:microsoft.quantum.glossary#operation)序列(或[門](xref:microsoft.quantum.glossary#gate)![)的方法,例如採樣](~/media/qpe.png)電路圖。 有關詳細資訊,請參閱[量子電路](xref:microsoft.quantum.concepts.circuits)。

## <a name="quantum-libraries"></a>量子庫

用於創建 Q# 程式[的操作](xref:microsoft.quantum.glossary#operation)、[函數](xref:microsoft.quantum.glossary#function)和[使用者定義類型的](xref:microsoft.quantum.glossary#user-defined-type)集合。 預設設定[檔](xref:microsoft.quantum.libraries.standard.intro)。 其他可用的圖書館包括[化學圖書館](xref:microsoft.quantum.chemistry.concepts.intro)、[數位圖書館](xref:microsoft.quantum.numerics.intro)與[機器學習庫](xref:microsoft.quantum.machine-learning.concepts.intro)。

## <a name="quantum-state"></a>量子狀態

分離量子系統的精確狀態,從中可以提取[測量](xref:microsoft.quantum.glossary#measurement)概率。 在量子計算中,量子模擬器使用此資訊來類比量子位如何回應操作。 有關詳細資訊,請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="qubit"></a>量子

量子資訊的基本單位,類似於經典計算中的一*點*。 有關詳細資訊,請參閱[Qubit](xref:microsoft.quantum.concepts.qubit)。

## <a name="repeat-until-success"></a>重複到成功

概率成功的量子演演演算法。 失敗后,例程將重試,直到成功(或已達到限制)。 有關詳細資訊,請參閱[重複直到成功 (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>標準程式庫

[安裝](xref:microsoft.quantum.glossary#operation)過程中與 Q# 編譯器一起安裝的操作、[函數](xref:microsoft.quantum.glossary#function),[以及使用者定義類型](xref:microsoft.quantum.glossary#user-defined-type)。 標準庫實現與目標計算機無關。 有關詳細資訊,請參閱[標準庫](xref:microsoft.quantum.libraries.standard.intro)。

## <a name="superposition"></a>疊加

量子計算中的概念是[量子位](xref:microsoft.quantum.glossary#qubit)是兩種狀態的線性組合,$ket_$和 ${1}$$$$$$,直到[被測量](xref:microsoft.quantum.glossary#measurement)為止。  有關詳細資訊,請參閱[什麼是量子計算](xref:microsoft.quantum.overview.what)。

## <a name="target-machine"></a>目標機器

將抽象量子程式降低到硬體或仿真的編譯目標。 這通常包括為多種目的重新寫入,包括門更換、用於糾錯的編碼、幾何佈局等。 有關詳細資訊,請參閱[量子模擬器和主機應用程式](xref:microsoft.quantum.machines)。

## <a name="teleportation"></a>遙傳

一種使用[糾纏](xref:microsoft.quantum.glossary#entanglement)和[測量](xref:microsoft.quantum.glossary#measurement)將一個[量子位](xref:microsoft.quantum.glossary#qubit)從一個地方再生數據或[量子態](xref:microsoft.quantum.glossary#quantum-state)的方法,而不實際移動量子位。  有關詳細資訊,請參閱[量子電路](xref:microsoft.quantum.concepts.circuits)並將其[全部放在一起](xref:microsoft.quantum.techniques.puttingittogether)。

## <a name="tuple"></a>Tuple

充當單個值的逗號分隔值的集合。 元組*的類型*由它包含的值類型定義。 在 Q# 中,tups 是[不可改變的](xref:microsoft.quantum.glossary#immutable),可以嵌套、包含數位或在陣列中使用。 有關詳細資訊,請參閱[中陣元類型](xref:microsoft.quantum.language.type-model#tuple-types)。

## <a name="unitary-operator"></a>單一運算子

逆與[等於其鄰接](xref:microsoft.quantum.glossary#adjoint)的運算符,即$UU[刀] = \id$。

## <a name="user-defined-type"></a>使用者定義型別

可稱為單個單元的內置或以前定義的類型的集合。 有關詳細資訊,請參閱[使用者定義的類型](xref:microsoft.quantum.language.type-model#user-defined-types)。