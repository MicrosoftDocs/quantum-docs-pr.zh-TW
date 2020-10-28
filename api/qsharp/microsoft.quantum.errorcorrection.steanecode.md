---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697926"
---
# <a name="steanecode-function"></a><span data-ttu-id="51744-102">SteaneCode 函式</span><span class="sxs-lookup"><span data-stu-id="51744-102">SteaneCode function</span></span>

<span data-ttu-id="51744-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="51744-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="51744-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="51744-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="51744-105">傳回代表⟦7、1、3⟧ Steane 程式碼編碼器的 CSS 值，以及具有就地發生症狀測量的解碼器。</span><span class="sxs-lookup"><span data-stu-id="51744-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="51744-106">輸出： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="51744-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="51744-107">CSS 型別的物件，它會收集所有相關資料，以執行⟦7、1、3⟧ Steane 程式碼的編碼和錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="51744-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="51744-108">備註</span><span class="sxs-lookup"><span data-stu-id="51744-108">Remarks</span></span>

<span data-ttu-id="51744-109">下列文章中找到此程式碼：</span><span class="sxs-lookup"><span data-stu-id="51744-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="51744-110">A.</span><span class="sxs-lookup"><span data-stu-id="51744-110">A.</span></span> <span data-ttu-id="51744-111">Steane，「多個粒子干擾和量子錯誤修正」，處理器。</span><span class="sxs-lookup"><span data-stu-id="51744-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="51744-112">羅伊。</span><span class="sxs-lookup"><span data-stu-id="51744-112">Roy.</span></span> <span data-ttu-id="51744-113">Soc. Lond。</span><span class="sxs-lookup"><span data-stu-id="51744-113">Soc. Lond.</span></span> <span data-ttu-id="51744-114">A452 (1996) pp 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="51744-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>