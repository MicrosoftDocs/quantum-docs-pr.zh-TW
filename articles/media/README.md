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
# <a name="readme"></a><span data-ttu-id="4c5fc-103">讀我檔案</span><span class="sxs-lookup"><span data-stu-id="4c5fc-103">README</span></span>
<span data-ttu-id="4c5fc-104">**重要**：若要讓影像在深色模式中正確呈現，您必須避免使用投影片。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-104">**IMPORTANT**: to have the images rendering properly in dark mode you must avoid transparencies.</span></span>
- <span data-ttu-id="4c5fc-105">對於 .jpg 檔案，您不需要做任何動作，因為檔案格式不支援透明元素。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-105">For .jpg files you don't need to do anything since the file format doesn't support transparent elements.</span></span>
- <span data-ttu-id="4c5fc-106">若是 .png 檔案，您必須加入白色背景，或將 Alpha 色板的值變更為100。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-106">For .png files you must add a white background or change the value of the alpha channel to 100.</span></span> <span data-ttu-id="4c5fc-107">在 Windows 中最簡單的方式是在 [油漆] 和 [儲存] 中開啟檔案，即可原始檔案。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-107">The easiest way to do this in Windows is by opening the file in Paint and saving, overwritting the original file.</span></span>
- <span data-ttu-id="4c5fc-108">針對 svg 檔案，您必須在最低層中加入白色矩形。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-108">For .svg files you must add a white rectangle in the lowest layer.</span></span> <span data-ttu-id="4c5fc-109">您可以使用引導 inkscape 來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="4c5fc-109">You can do this with Inkscape:</span></span>
  - <span data-ttu-id="4c5fc-110">開啟 svg 檔案。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-110">Open the .svg file.</span></span>
  - <span data-ttu-id="4c5fc-111">選取 [正方形 maker] 工具，並在原始圖形上方繪製白色矩形。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-111">Select the square maker tool and draw a white rectangle on top of the original figure.</span></span>
  - <span data-ttu-id="4c5fc-112">按一下深色箭號或按 F1 鍵，選取 [選取和轉換物件] 工具。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-112">Select the tool "Select and transform objects" by clicking in the dark arrow or pressing F1.</span></span>
  - <span data-ttu-id="4c5fc-113">選取矩形時，請按一下工具列元素的 [底部選取範圍 (End) ]。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-113">While having the rectangle selected, click in the toolbar element "Lower selection to bottom (End)".</span></span>
  - <span data-ttu-id="4c5fc-114">以滑鼠或方向鍵調整矩形。</span><span class="sxs-lookup"><span data-stu-id="4c5fc-114">Adjust the rectangle with the mouse or the arrow keys.</span></span>
