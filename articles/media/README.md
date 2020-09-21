---
title: 媒體讀我檔案
description: 上傳影像的秘訣
author: geduardo
ms.author: v-edsanc
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: bf28f57820e95bbbf81f5ac7ade582d89b945a26
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834528"
---
# <a name="readme"></a>讀我檔案
**重要**：若要讓影像在深色模式中正確呈現，您必須避免使用投影片。
- 對於 .jpg 檔案，您不需要做任何動作，因為檔案格式不支援透明元素。
- 若是 .png 檔案，您必須加入白色背景，或將 Alpha 色板的值變更為100。 在 Windows 中最簡單的方式是在 [油漆] 和 [儲存] 中開啟檔案，即可原始檔案。
- 針對 svg 檔案，您必須在最低層中加入白色矩形。 您可以使用引導 inkscape 來執行此動作：
  - 開啟 svg 檔案。
  - 選取 [正方形 maker] 工具，並在原始圖形上方繪製白色矩形。
  - 按一下深色箭號或按 F1 鍵，選取 [選取和轉換物件] 工具。
  - 選取矩形時，請按一下工具列元素的 [底部選取範圍 (End) ]。
  - 以滑鼠或方向鍵調整矩形。
