---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200878"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="13e97-102">FiveQubitCode 函式</span><span class="sxs-lookup"><span data-stu-id="13e97-102">FiveQubitCode function</span></span>

<span data-ttu-id="13e97-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="13e97-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="13e97-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13e97-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13e97-105">傳回 QECC 值，代表⟦5，1，3⟧代碼編碼器，以及具有就地發生症狀測量的解碼器。</span><span class="sxs-lookup"><span data-stu-id="13e97-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="13e97-106">輸出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="13e97-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="13e97-107">藉由指定類型，傳回量子錯誤修正程式碼的執行 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="13e97-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="13e97-108">備註</span><span class="sxs-lookup"><span data-stu-id="13e97-108">Remarks</span></span>

<span data-ttu-id="13e97-109">下列兩份檔中找到此程式碼：</span><span class="sxs-lookup"><span data-stu-id="13e97-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="13e97-110">C.</span><span class="sxs-lookup"><span data-stu-id="13e97-110">C.</span></span> <span data-ttu-id="13e97-111">H.</span><span class="sxs-lookup"><span data-stu-id="13e97-111">H.</span></span> <span data-ttu-id="13e97-112">Bennett、d. DiVincenzo、J. A。</span><span class="sxs-lookup"><span data-stu-id="13e97-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="13e97-113">Smolin 和 W. K。</span><span class="sxs-lookup"><span data-stu-id="13e97-113">Smolin and W. K.</span></span> <span data-ttu-id="13e97-114">Wootters、「混合狀態纏結與量子錯誤修正」、Phys. A、54 (1996) pp 3824-3851; https://arxiv.org/abs/quant-ph/9604024 和</span><span class="sxs-lookup"><span data-stu-id="13e97-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="13e97-115">R.</span><span class="sxs-lookup"><span data-stu-id="13e97-115">R.</span></span> <span data-ttu-id="13e97-116">Laflamme、c. Miquel、J-phone。</span><span class="sxs-lookup"><span data-stu-id="13e97-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="13e97-117">巴斯和 W. H。</span><span class="sxs-lookup"><span data-stu-id="13e97-117">Paz and W. H.</span></span> <span data-ttu-id="13e97-118">Zurek，「完美的量子錯誤矯正碼」 Phys Lett。</span><span class="sxs-lookup"><span data-stu-id="13e97-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="13e97-119">77 (1996) pp 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="13e97-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>