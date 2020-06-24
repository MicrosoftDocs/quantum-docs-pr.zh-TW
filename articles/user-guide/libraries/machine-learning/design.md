---
title: 使用 QDK 設計您自己的分類器
description: 瞭解為配量以電路為中心的分類器設計線路模型的基本概念。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: b304b9d1a15f164f4dfe758aaed31b7b2369b18c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274683"
---
# <a name="design-your-own-classifier"></a>設計您自己的分類器

在本指南中，您將瞭解在配量以電路為中心的分類器中，設計線路模型背後的基本概念。

如同傳統深度學習，選擇特定架構並沒有一般規則。 視問題而定，某些架構的執行效果會高於其他架構。 但是，在設計線路時，有些概念可能會很有用：

- 大量參數意味著更有彈性的模型，這可能適合用來繪製複雜的分類界限，但這可能也會更容易過度學習。

- Qubits 之間的 Entangling 閘道對於捕捉配量功能之間的相互關聯而言，是不可或缺的。

## <a name="how-to-build-a-classifier-with-q"></a>如何使用 Q 建立分類器\#

為了建立分類器，我們將會串連線路模型中的參數化控制旋轉。 若要這麼做，我們可以使用配量 [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) Machine Learning 程式庫中所定義的類型。 此類型會接受四個引數，以決定：目標 qubit 的索引、控制項 qubits 的索引陣列、旋轉軸，以及定義模型之參數陣列中相關參數的索引。

我們來看一下分類器的範例。 在[半衛星範例](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)中，我們可以找到檔案中定義的下列分類器 `Training.qs` 。

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

我們在這裡定義的是一個函式，它會傳回 `ControlledRotation` 元素陣列，並搭配參數陣列和偏差來定義我們的 [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) 。 此類型是配量 Machine Learning 程式庫中的基礎，而且會定義分類器。 上述函數中定義的線路是分類器的一部分，其中資料集的每個範例都包含兩個功能。 因此，我們只需要兩個 qubits。 線路的圖形表示如下：

 ![線路模型範例](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>使用程式庫函式來撰寫閘道的層級

假設我們有一個資料集，每個實例都有784的功能，例如 MNIST 資料集的28×28圖元影像。 在此情況下，線路的寬度會變得夠大，因此，每個個別閘道的書寫會變成可行但不切實際的工作。 這就是為什麼量子 Machine Learning 程式庫提供一組工具來自動產生參數化旋轉層級。 例如，函式會 [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) 傳回一個陣列，其中包含指定軸的未受控制單一 qubit 旋轉，並針對暫存器中的每個 qubit 逐一旋轉，每個都是以不同的模型參數來參數化。 例如，會傳回 `LocalRotationsLayer(4, X)` 下列一組閘道：

 ![本機旋轉層](~/media/local_rotations_layer.PNG)

我們建議您探索配[量 Machine Learning 程式庫的 API 參考](xref:microsoft.quantum.machinelearning)，以探索可簡化電路設計的所有工具。

## <a name="next-steps"></a>後續步驟

 在範例所提供的範例中，嘗試不同的結構。 您是否看到模型效能有任何變更？ 在下一個教學課程中， [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) 您將瞭解如何載入資料集以嘗試和探索新的分類器架構。
