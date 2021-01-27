---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853063"
---
# <a name="steanecode-function"></a><span data-ttu-id="84559-102">SteaneCode 函式</span><span class="sxs-lookup"><span data-stu-id="84559-102">SteaneCode function</span></span>

<span data-ttu-id="84559-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="84559-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="84559-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84559-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84559-105">傳回代表⟦7、1、3⟧ Steane 程式碼編碼器的 CSS 值，以及具有就地發生症狀測量的解碼器。</span><span class="sxs-lookup"><span data-stu-id="84559-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="84559-106">輸出： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="84559-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="84559-107">CSS 型別的物件，它會收集所有相關資料，以執行⟦7、1、3⟧ Steane 程式碼的編碼和錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="84559-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="84559-108">備註</span><span class="sxs-lookup"><span data-stu-id="84559-108">Remarks</span></span>

<span data-ttu-id="84559-109">下列文章中找到此程式碼：</span><span class="sxs-lookup"><span data-stu-id="84559-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="84559-110">A.</span><span class="sxs-lookup"><span data-stu-id="84559-110">A.</span></span> <span data-ttu-id="84559-111">Steane，「多個粒子干擾和量子錯誤修正」，處理器。</span><span class="sxs-lookup"><span data-stu-id="84559-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="84559-112">羅伊。</span><span class="sxs-lookup"><span data-stu-id="84559-112">Roy.</span></span> <span data-ttu-id="84559-113">Soc. Lond。</span><span class="sxs-lookup"><span data-stu-id="84559-113">Soc. Lond.</span></span> <span data-ttu-id="84559-114">A452 (1996) pp 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="84559-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>