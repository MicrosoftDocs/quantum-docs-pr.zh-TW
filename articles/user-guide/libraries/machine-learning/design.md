---
title: 使用 QDK 設計您自己的分類器
description: 瞭解為量子線路中心分類器設計電路模型的基本概念。
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3515279dd4d03b2a512035af0b13e084dd91f9dc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835701"
---
# <a name="design-your-own-classifier"></a>設計您自己的分類器

在本指南中，您將瞭解以量子線路為中心的分類器之電路模型設計背後的基本概念。

如同傳統深度學習，沒有選擇特定架構的一般規則。 視問題而定，某些架構會比其他架構執行得更好。 但在設計線路時，有些概念可能很有用：

- 大量的參數表示更有彈性的模型，這可能適合用來繪製複雜的分類界限，但也可能更容易過度學習。

- 量子位之間的 Entangling 閘道對於捕捉量子功能之間的相互關聯是不可或缺的。

## <a name="how-to-build-a-classifier-with-q"></a>如何使用 Q 建立分類器\#

為了建立分類器，我們將會在電路模型中串連參數化控制的旋轉。 若要這樣做，我們可以使用 [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) 量子 Machine Learning 程式庫中定義的類型。 這個型別接受四個引數來決定：目標量子位的索引、控制項量子位的索引陣列、旋轉軸，以及定義模型的參數陣列中相關聯參數的索引。

讓我們看看分類器的範例。 在 [半衛星範例](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)中，我們可以在檔案中找到下列定義的分類器 `Training.qs` 。

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

我們在這裡定義的是一種函式，它會傳回 `ControlledRotation` 元素陣列，連同參數陣列，而偏差將會定義我們的 [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) 。 這種類型在量子 Machine Learning 程式庫中是基本的，而且會定義分類器。 上述函數中定義的電路是分類器的一部分，其中資料集的每個範例都包含兩項功能。 因此，我們只需要兩個量子位。 電路的圖形標記法如下：

 ![電路模型範例](~/media/circuit_model_1.PNG)

請注意，根據預設，量子 Machine Learning 程式庫的作業會測量註冊的最後一個量子位，以估計分類機率。 當您設計線路時，請記住這一點。

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>使用程式庫函數來寫入閘道層

假設我們的資料集具有每個實例784的功能，例如28×28圖元的影像，例如 MNIST 資料集。 在此情況下，線路的寬度會變得夠大，因此以手動方式撰寫每個閘道會成為可能但不實用的工作。 這就是量子 Machine Learning 程式庫提供一組工具來自動產生參數化旋轉層級的原因。 例如，此函式會在 [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) 指定的軸上傳回未受控制的單一量子位旋轉陣列，其中每個量子位都有一個旋轉，而每個都是由不同的模型參數所參數化。 例如，會傳回 `LocalRotationsLayer(4, X)` 下列一組閘道：

 ![本機旋轉圖層](~/media/local_rotations_layer.PNG)

建議您探索 [量子 Machine Learning 程式庫的 API 參考](xref:microsoft.quantum.machinelearning) ，以探索可簡化電路設計的所有工具。

## <a name="next-steps"></a>後續步驟

 在範例所提供的範例中，嘗試不同的結構。 您是否看到模型效能的任何變更？ 在下一個教學課程中， [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) 您將瞭解如何載入資料集，以嘗試及探索新的分類器架構。
