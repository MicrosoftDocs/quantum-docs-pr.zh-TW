---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200470"
---
# <a name="steanecode-function"></a><span data-ttu-id="88dd0-102">SteaneCode 函式</span><span class="sxs-lookup"><span data-stu-id="88dd0-102">SteaneCode function</span></span>

<span data-ttu-id="88dd0-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="88dd0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="88dd0-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88dd0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88dd0-105">傳回代表⟦7、1、3⟧ Steane 程式碼編碼器的 CSS 值，以及具有就地發生症狀測量的解碼器。</span><span class="sxs-lookup"><span data-stu-id="88dd0-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="88dd0-106">輸出： [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="88dd0-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="88dd0-107">CSS 型別的物件，它會收集所有相關資料，以執行⟦7、1、3⟧ Steane 程式碼的編碼和錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="88dd0-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="88dd0-108">備註</span><span class="sxs-lookup"><span data-stu-id="88dd0-108">Remarks</span></span>

<span data-ttu-id="88dd0-109">下列文章中找到此程式碼：</span><span class="sxs-lookup"><span data-stu-id="88dd0-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="88dd0-110">A.</span><span class="sxs-lookup"><span data-stu-id="88dd0-110">A.</span></span> <span data-ttu-id="88dd0-111">Steane，「多個粒子干擾和量子錯誤修正」，處理器。</span><span class="sxs-lookup"><span data-stu-id="88dd0-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="88dd0-112">羅伊。</span><span class="sxs-lookup"><span data-stu-id="88dd0-112">Roy.</span></span> <span data-ttu-id="88dd0-113">Soc. Lond。</span><span class="sxs-lookup"><span data-stu-id="88dd0-113">Soc. Lond.</span></span> <span data-ttu-id="88dd0-114">A452 (1996) pp 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="88dd0-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>