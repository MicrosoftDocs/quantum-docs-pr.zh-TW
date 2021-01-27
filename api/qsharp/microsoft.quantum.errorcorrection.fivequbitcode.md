---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853148"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="d21c2-102">FiveQubitCode 函式</span><span class="sxs-lookup"><span data-stu-id="d21c2-102">FiveQubitCode function</span></span>

<span data-ttu-id="d21c2-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d21c2-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d21c2-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d21c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d21c2-105">傳回 QECC 值，代表⟦5，1，3⟧代碼編碼器，以及具有就地發生症狀測量的解碼器。</span><span class="sxs-lookup"><span data-stu-id="d21c2-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="d21c2-106">輸出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="d21c2-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="d21c2-107">藉由指定類型，傳回量子錯誤修正程式碼的執行 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="d21c2-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="d21c2-108">備註</span><span class="sxs-lookup"><span data-stu-id="d21c2-108">Remarks</span></span>

<span data-ttu-id="d21c2-109">下列兩份檔中找到此程式碼：</span><span class="sxs-lookup"><span data-stu-id="d21c2-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="d21c2-110">C.</span><span class="sxs-lookup"><span data-stu-id="d21c2-110">C.</span></span> <span data-ttu-id="d21c2-111">H.</span><span class="sxs-lookup"><span data-stu-id="d21c2-111">H.</span></span> <span data-ttu-id="d21c2-112">Bennett、d. DiVincenzo、J. A。</span><span class="sxs-lookup"><span data-stu-id="d21c2-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="d21c2-113">Smolin 和 W. K。</span><span class="sxs-lookup"><span data-stu-id="d21c2-113">Smolin and W. K.</span></span> <span data-ttu-id="d21c2-114">Wootters、「混合狀態纏結與量子錯誤修正」、Phys. A、54 (1996) pp 3824-3851; https://arxiv.org/abs/quant-ph/9604024 和</span><span class="sxs-lookup"><span data-stu-id="d21c2-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="d21c2-115">R.</span><span class="sxs-lookup"><span data-stu-id="d21c2-115">R.</span></span> <span data-ttu-id="d21c2-116">Laflamme、c. Miquel、J-phone。</span><span class="sxs-lookup"><span data-stu-id="d21c2-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="d21c2-117">巴斯和 W. H。</span><span class="sxs-lookup"><span data-stu-id="d21c2-117">Paz and W. H.</span></span> <span data-ttu-id="d21c2-118">Zurek，「完美的量子錯誤矯正碼」 Phys Lett。</span><span class="sxs-lookup"><span data-stu-id="d21c2-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="d21c2-119">77 (1996) pp 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="d21c2-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>