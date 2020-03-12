---
title: 媒體讀我檔案
description: 上傳影像的秘訣
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: a4922e28a8fc5ddfb4cbc80302e23869154234d8
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024180"
---
# <a name="readme"></a><span data-ttu-id="42a81-103">讀我檔案</span><span class="sxs-lookup"><span data-stu-id="42a81-103">README</span></span>
<span data-ttu-id="42a81-104">**重要**：若要在深色模式中正確轉譯影像，您必須避免使用透明度。</span><span class="sxs-lookup"><span data-stu-id="42a81-104">**IMPORTANT**: to have the images rendering properly in dark mode you must avoid transparencies.</span></span>
- <span data-ttu-id="42a81-105">針對 .jpg 檔案，您不需要執行任何動作，因為檔案格式不支援透明元素。</span><span class="sxs-lookup"><span data-stu-id="42a81-105">For .jpg files you don't need to do anything since the file format doesn't support transparent elements.</span></span>
- <span data-ttu-id="42a81-106">若是 .png 檔案，您必須加入白色背景，或將 Alpha 色板的值變更為100。</span><span class="sxs-lookup"><span data-stu-id="42a81-106">For .png files you must add a white background or change the value of the alpha channel to 100.</span></span> <span data-ttu-id="42a81-107">在 Windows 中執行此動作的最簡單方式是在 [繪製並儲存] 中開啟檔案，即可原始檔案。</span><span class="sxs-lookup"><span data-stu-id="42a81-107">The easiest way to do this in Windows is by opening the file in Paint and saving, overwritting the original file.</span></span>
- <span data-ttu-id="42a81-108">若是 svg 檔案，您必須在最低層中新增白色矩形。</span><span class="sxs-lookup"><span data-stu-id="42a81-108">For .svg files you must add a white rectangle in the lowest layer.</span></span> <span data-ttu-id="42a81-109">您可以使用引導 inkscape 來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="42a81-109">You can do this with Inkscape:</span></span>
  - <span data-ttu-id="42a81-110">開啟 svg 檔案。</span><span class="sxs-lookup"><span data-stu-id="42a81-110">Open the .svg file.</span></span>
  - <span data-ttu-id="42a81-111">選取 [方形 maker] 工具，並在原始圖表頂端繪製一個白色矩形。</span><span class="sxs-lookup"><span data-stu-id="42a81-111">Select the square maker tool and draw a white rectangle on top of the original figure.</span></span>
  - <span data-ttu-id="42a81-112">按一下深色箭號或按 F1 鍵，以選取工具「選取和轉換物件」。</span><span class="sxs-lookup"><span data-stu-id="42a81-112">Select the tool "Select and transform objects" by clicking in the dark arrow or pressing F1.</span></span>
  - <span data-ttu-id="42a81-113">選取矩形時，按一下工具列元素中的 [下方選取範圍] （結束）。</span><span class="sxs-lookup"><span data-stu-id="42a81-113">While having the rectangle selected, click in the toolbar element "Lower selection to bottom (End)".</span></span>
  - <span data-ttu-id="42a81-114">使用滑鼠或方向鍵調整矩形。</span><span class="sxs-lookup"><span data-stu-id="42a81-114">Adjust the rectangle with the mouse or the arrow keys.</span></span>
