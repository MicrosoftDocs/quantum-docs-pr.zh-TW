---
title: '全部整合-Q # 技術 |Microsoft Docs'
description: '全部整合-Q # 技術'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 3605826da159757d4b321dbf4ec6acd7f4e6be05
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820159"
---
# <a name="putting-it-all-together-teleportation"></a>全部放在一起： Teleportation #
讓我們回到配量[線路](xref:microsoft.quantum.concepts.circuits)中所定義之 teleportation 電路的範例。 我們將使用它來說明我們到目前為止所學到的概念。 以下針對不熟悉理論的使用者提供配量 teleportation 的說明，後面接著 Q # 中的程式碼執行逐步解說。 

## <a name="quantum-teleportation-theory"></a>量子 Teleportation：理論
「量子 teleportation」是一種將不明的量子狀態（我們將其稱為「__訊息__」）從某個位置的 qubit 傳送至另一個位置中 qubit 的技術（我們會分別將這些 qubits 稱為「__此處__」和「此處」）。 我們可以使用 Dirac 標記法，將__訊息__表示為向量： 

$ $ \ket{\psi} = \Alpha\ket{0} + \Beta\ket{1} $ $

因為我們不知道 $ \Alpha $ 和 $ \Beta $ 的值，所以我們無法得知__訊息__qubit 的狀態。

### <a name="step-1-create-an-entangled-state"></a>步驟1：建立光子狀態
為了傳送__訊息__，我們需要 qubit__這裡__的光子__與 qubit。__ 這是藉由套用 Hadamard 閘道，後面接著 CNOT-CONTAINS 閘道來達成。 讓我們看看這些閘道作業背後的數學運算。

我們會從__這裡__的 qubits 開始，__並在__$ \ket{0}$ 狀態中。 Entangling 這些 qubits 之後，它們就會處於下列狀態：

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} （\ket{00} + \ket{11}） $ $

### <a name="step-2-send-the-message"></a>步驟2：傳送訊息
若要傳送__訊息__，我們首先要以__message__ __qubit 和 qubit__做為輸入來套用 cnot-contains 閘道（__訊息__qubit 是控制項，而__這裡__qubit 是目標 qubit，在此例中為）。 可以寫入此輸入狀態：

$ $ \ket{\psi}\ket{\phi ^ +} = （\Alpha\ket{0} + \Beta\ket{1}）（\frac{1}{\sqrt{2}} （\ket{00} + \ket{11}）） $ $

這會展開為：

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\Beta}{\sqrt{2}} \ket{100} + \frac{\Beta}{\sqrt{2}} \ket{111} $ $

提醒您，當控制項 qubit 為1時，CNOT-CONTAINS 閘道會翻轉目標 qubit。 例如，$ \ket{000}$ 的輸入將不會變更，因為第一個 qubit （控制項）為0。 不過，在第一個 qubit 為1的情況下，例如 $ \ket{100}$ 的輸入。 在此實例中，輸出為 $ \ket{110}$，因為第二個 qubit （目標）是由 CNOT-CONTAINS 閘道翻轉。

現在，讓我們在 CNOT-CONTAINS 閘道對上述輸入進行動作之後，考慮我們的輸出。 結果如下：

$ $ \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\Beta}{\sqrt{2}} \ket{110} + \frac{\Beta}{\sqrt{2}} \ket{101} $ $

傳送__訊息__的下一個步驟是將 Hadamard 閘道套用至__訊息__qubit （這是每個詞彙的第一個 qubit）。 

提醒您，Hadamard 閘道會執行下列動作：

輸入 | 輸出
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} （\ket{0} + \ket{1}） $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} （\ket{0}-\ket{1}） $

如果我們將 Hadamard 閘道套用至上述輸出中每個詞彙的第一個 qubit，我們會得到下列結果：

$ $ \frac{\Alpha}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0} + \ket{1}）） \ket{00} + \frac{\Alpha}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0} + \ket{1}）） \ket{11} + \frac{\Beta}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0}-\ket{1}）） \ket{10} + \frac{\Beta}{\sqrt{2}} （\frac{1}{\sqrt{2}} （\ket{0}-\ket{1}）） \ket{01} $ $

請注意，每個詞彙都有 $2 \frac{1}{\sqrt{2}} $ 因素。 我們可以將這些結果相乘，以提供下列結果：

$ $ \frac{\Alpha}{2}（\ket{0} + \ket{1}） \ket{00} + \frac{\Alpha}{2}（\ket{0} + \ket{1}） \ket{11} + \frac{\Beta}{2}（\ket{0}-\ket{1}） \ket{10} + \frac{\Beta}{2}（\ket{0}-\ket{1}） \ket{01} $ $

$ \Frac{1}{2}$ 因素是每個詞彙通用的，因此我們現在可以將其帶到括弧外：

$ $ \frac{1}{2}\big [\Alpha （\ket{0} + \ket{1}） \ket{00} + \Alpha （\ket{0} + \ket{1}） \ket{11} + \Beta （\ket{0}-\ket{1}） \ket{10} + \Beta （\ket{0}-\ket{1}） \ket{01}\big] $ $

然後，我們可以將每個詞彙的括弧相乘，以提供：

$ $ \frac{1}{2}\big [\Alpha\ket{000} + \Alpha\ket{100} + \Alpha\ket{011} + \Alpha\ket{111} + \Beta\ket{010}-\Beta\ket{110} + \Beta\ket{001}-\Beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>步驟3：測量結果

由於__這裡__ __還有__光子，因此__這裡__的任何測量都會影響到__該處__的狀態。 如果我們測量第一個和第二個 qubit （__訊息__和__此處__），我們就可以瞭解因為會任何牽連的這個屬性而__存在__的狀態。 

* 如果我們測量並取得結果00，重迭會折迭，只留下與此結果一致的詞彙。 這是 $ \Alpha\ket{000} + \Beta\ket{001}$。 這可以重構為 $ \ket{00}（\Alpha\ket{0} + \Beta\ket{1}） $。 因此 __，如果__我們將第一個和第二個 qubit 測量成00，我們知道第三個 qubit 的狀態是 $ （\Alpha\ket{0} + \Beta\ket{1}） $。
* 如果我們測量並取得結果01，則重迭會折迭，只留下與此結果一致的詞彙。 這是 $ \Alpha\ket{011} + \Beta\ket{010}$。 這可以重構為 $ \ket{01}（\Alpha\ket{1} + \Beta\ket{0}） $。 因此 __，如果__我們將第一個和第二個 qubit 測量成01，我們知道第三個 qubit 的狀態是 $ （\Alpha\ket{1} + \Beta\ket{0}） $。
* 如果我們測量結果10，就會折迭重迭，只留下與此結果一致的條款。 這是 $ \Alpha\ket{100}-\Beta\ket{101}$。 這可以重構為 $ \ket{10}（\Alpha\ket{0}-\Beta\ket{1}） $。 因此 __，如果__我們將第一個和第二個 qubit 測量為10，我們知道第三個 qubit 的狀態是 $ （\Alpha\ket{0}-\Beta\ket{1}） $。
* 如果我們測量並得到結果11，重迭會折迭，只留下與此結果一致的詞彙。 這是 $ \Alpha\ket{111}-\Beta\ket{110}$。 這可以重構為 $ \ket{11}（\Alpha\ket{1}-\Beta\ket{0}） $。 因此 __，如果__我們將第一個和第二個 qubit 測量為11，我們知道第三個 qubit 的狀態是 $ （\Alpha\ket{1}-\Beta\ket{0}） $。

### <a name="step-4-interpret-the-result"></a>步驟4：解讀結果

提醒您，我們想要傳送的原始__訊息__是：

$ $ \ket{\psi} = \Alpha\ket{0} + \Beta\ket{1} $ $

我們需要__取得此狀態的 qubit，__ 讓 [已接收] 狀態是預期的狀態。 

* 如果我們測量並得到00的__結果，則__第三個 qubit 會處於 state $ （\Alpha\ket{0} + \Beta\ket{1}） $。 由於這是預期的__訊息__，因此不需要進行任何變更。
* 如果我們測量並得到01的__結果，則__第三個 qubit 會處於 state $ （\Alpha\ket{1} + \Beta\ket{0}） $。 這與預期的__訊息__不同，但套用 NOT 閘道會提供所需的狀態 $ （\Alpha\ket{0} + \Beta\ket{1}） $。
* 如果我們測量並得到10的__結果，則__第三個 qubit 會處於 state $ （\Alpha\ket{0}-\Beta\ket{1}） $。 這與預期的__訊息__不同，不過，套用 Z 閘道會提供所需的狀態 $ （\Alpha\ket{0} + \Beta\ket{1}） $。
* 如果我們測量並得到11的__結果，則__第三個 qubit 會處於 state $ （\Alpha\ket{1}-\Beta\ket{0}） $。 這與預期的__訊息__不同，但套用的 NOT 閘道後面接著 Z 閘道會提供所需的 state $ （\Alpha\ket{0} + \Beta\ket{1}） $。

總而言之，如果我們測量，而第一個 qubit 是1，則會套用 Z 閘道。 如果我們測量，而第二個 qubit 是1，則會套用 NOT 閘道。

### <a name="summary"></a>摘要
如下所示，這是用來執行 teleportation 的文字書本量子線路。 從左至右移動，您可以看到：
- 步驟1：__在這裡__Entangling __，並__套用 HADAMARD 閘道和 cnot-contains 閘道。
- 步驟2：使用 CNOT-CONTAINS 閘道和 Hadamard 閘道來傳送__訊息__。
- 步驟3：測量第一個和第二個 qubits、__訊息__和__此處__。
- 步驟4：套用非閘道或 Z 閘道，視步驟3中的測量結果而定。

![' 傳送（msg： Qubit，有： Qubit）： Unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>量子 Teleportation：程式碼

我們有配量 teleportation 的線路：

![' 傳送（msg： Qubit，有： Qubit）： Unit '](~/media/teleportation.svg)

我們現在可以將此配量電路中的每個步驟轉譯為 Q #。

### <a name="step-0-definition"></a>步驟0：定義
當我們執行 teleportation 時，我們必須知道想要傳送的__訊息__，以及我們想要傳送給它的位置（__這裡__）。 基於這個理由，我們一開始會定義一個新的「傳送」作業，以提供兩個 qubits 做為引數，`msg` 和 `there`：

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

我們也需要配置一個 qubit `here`，以 `using` 組塊達成：

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>步驟1：建立光子狀態
然後，我們可以使用 @"microsoft.quantum.intrinsic.h" 和 @"microsoft.quantum.intrinsic.cnot" 作業，在 `here` 和 `there` 之間建立光子組：

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>步驟2：傳送訊息
接著，我們會使用下一個 $ \operatorname{CNOT} $ 和 $H $ 閘道來移動訊息 qubit：

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>步驟 3 & 4：測量並解讀結果
最後，我們會使用 @"microsoft.quantum.intrinsic.m" 來執行測量，並執行必要的閘道作業，以取得所需的狀態，如 `if` 的語句所表示：

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

這會完成 teleportation 運算子的定義，因此我們可以解除配置 `here`、結束主體，並結束作業。

```qsharp
    }
}
```
