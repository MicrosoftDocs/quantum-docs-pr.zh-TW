---
title: 載入傳統資料
description: 瞭解如何載入您自己的資料集，以使用 Microsoft 量子開發工具組 (QDK) 來定型分類器模型。
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7ebfe085e50d4647fdb1027250cf3134f8d8f8c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856462"
---
# <a name="load-and-classify-your-own-datasets"></a>載入和分類您自己的資料集

在這個簡短的教學課程中，我們將瞭解如何載入您自己的資料集，以使用量子開發工具組 (QDK) 來定型分類器模型。

強烈建議您使用標準化的序列化格式，例如 [JSON](https://en.wikipedia.org/wiki/JSON) 檔案來儲存您的資料。
這類格式提供與 Python 和 .NET 生態系統等不同架構的高度相容性。
尤其是，我們建議使用我們的範本來載入資料，如此您就可以直接從範例複製並貼上程式碼。

## <a name="template-for-loading-your-datasets"></a>載入資料集的範本

假設我們有一個訓練資料集 $ (x，y) $ 大小 $N = $2，其中每個實例 $x _i $ of $x $ 有三個功能： $x _ {i1} $、$x _ {i2} $ 和 $x _ {i3} $。
驗證資料集具有相同的結構。
這些底下可以使用 `data.json` 類似下列的檔案來表示：

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

假設我們有一個小型資料集，其具有不同貓和狗的高度和加權。 這個資料集很小，無法定型模型，但也足以顯示載入資料集的程式。

| 高度 (m)  | 重量 (公斤) | 動物 |
|-----------|------------|--------|
| 0.54      | 30         | 狗    |
| 0.30      | 8          | 貓    |
| 0.91      | 44         | 狗    |
| 0.86      | 31          | 狗    |
| 0.32      | 5         | 貓    |
| 0.25      | 4          | 貓    |

程序如下：

- 首先，我們需要將資料集分成定型和驗證。 在此情況下，我們可以採用前三個範例來進行訓練，並使用其餘範例進行驗證。 一般而言，若要隨機取樣定型和驗證資料集，以避免定型資料中有不必要的偏差，通常是很好的作法。
- 其次，我們需要將數值標籤指派給每個類別。 請注意，目前 QML 程式庫只會認可二元分類問題。 因此，我們會將標籤0指派給類別 `Dog` ，並將數位1指派給類別 `Cat` 。
- 最後，我們會使用資料集的資料來填滿範本。 請注意，對於大型資料集，您應該建立一個小型的腳本，以自動從您的特定資料集產生範本。 此腳本將取決於您的資料集原始格式。

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

當您將資料序列化為 JSON 檔案之後，您可以使用您選擇的主機語言提供的 JSON 程式庫將它載入。

### <a name="python"></a>[Python](#tab/tabid-python)

Python 提供使用 JSON 序列化資料的 [內建 `json` 套件](https://docs.python.org/3.7/library/json.html) ：

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

.NET Core 平臺提供使用 JSON 序列化資料的[ `System.Text.Json` 封裝](https://www.nuget.org/packages/System.Text.Json)：

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>後續步驟

現在您已準備好開始使用您自己的資料集來執行您自己的實驗。 試用不同的分類器和資料集，並參與共用您的結果的社區！
