---
title: 正在載入傳統資料
description: 瞭解如何載入您自己的資料集，以使用 Microsoft Quantum Development Kit (QDK) 來定型分類器模型。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 26ba7411c9ade1d6c4b606e8c12c10ade18fc584
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868826"
---
# <a name="load-and-classify-your-own-datasets"></a>載入和分類您自己的資料集

在這個簡短的教學課程中，我們將學習如何載入您自己的資料集，以使用 (QDK) 的量子開發工具組來定型分類器模型。

我們強烈建議使用標準化的序列化格式，例如[JSON](https://en.wikipedia.org/wiki/JSON)檔案來儲存您的資料。
這種格式會提供與不同架構（例如 Python 和 .NET 生態系統）的高度相容性。
特別是，我們建議使用我們的範本來載入資料，讓您可以直接從範例複製並貼上程式碼。

## <a name="template-for-loading-your-datasets"></a>用於載入資料集的範本

假設我們有一個訓練資料集 $ (x，y) $ 大小 $N = $2，其中每個實例 $x _i $ of $x $ 都有三個功能： $x _ {i1} $、$x _ {i2} $ 和 $x _ {i3} $。
驗證資料集具有相同的結構。
這些 datsets 可以使用 `data.json` 類似下列的檔案來表示：

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>使用範本的範例

假設我們有一個具有不同貓和狗之高度和加權的小型資料集。 此資料集非常小，可將模型定型，但足以顯示載入資料集的程式。

| 高度 (m)  | 權數 (公斤)  | 動物 |
|-----------|------------|--------|
| 0.54      | 30         | 狗    |
| 0.30      | 8          | Cat    |
| 0.91      | 44         | 狗    |
| 0.86      | 31          | 狗    |
| 0.32      | 5         | Cat    |
| 0.25      | 4          | Cat    |

程序如下：

- 首先，我們需要將資料集分隔成定型和驗證。 在此情況下，我們可以只接受前三個範例來進行定型，並使用其餘的範例進行驗證。 一般而言，若要在定型資料中隨機取樣定型和驗證資料集，以避免不必要的偏差，這是很好的作法。
- 其次，我們必須將數值標籤指派給每個類別。 請注意，在此時間點，QML 程式庫只會 dynamicexpression 二元分類問題。 因此，我們會將標籤0指派給類別 `Dog` ，並將數位1指派給類別 `Cat` 。
- 最後，我們會使用來自資料集的資料來填滿範本。 請注意，對於大型資料集，您應該建立一個小型的腳本，以從您的特定資料集自動產生範本。 此腳本將取決於資料集的原始格式。

針對我們的資料集，檔案 `data.json` 為：

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>載入資料

將資料序列化為 JSON 檔案之後，您可以使用您選擇的主機語言所提供的 JSON 程式庫，將其載入至。

### <a name="python"></a>[Python](#tab/tabid-python)

Python 提供用於處理 JSON 序列化資料的[內建 `json` 套件](https://docs.python.org/3.7/library/json.html)：

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

.NET Core 平臺提供[ `System.Text.Json` 封裝](https://www.nuget.org/packages/System.Text.Json)以使用 JSON 序列化的資料：

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>後續步驟

現在您已準備好使用自己的資料集開始執行自己的實驗。 請嘗試不同的分類器和資料集，並參與分享您結果的社區！
