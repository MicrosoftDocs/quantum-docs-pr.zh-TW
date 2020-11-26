---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 2d0b50bd2467fc01caacbbcb22f98c59a2d13922
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201218"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="504a6-102">BitFlipCode 函式</span><span class="sxs-lookup"><span data-stu-id="504a6-102">BitFlipCode function</span></span>

<span data-ttu-id="504a6-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="504a6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="504a6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="504a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="504a6-105">傳回 QECC 值，表示⟦3、1、1⟧位翻轉程式碼編碼器，以及具有就地的症狀測量的解碼器。</span><span class="sxs-lookup"><span data-stu-id="504a6-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="504a6-106">輸出： [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="504a6-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="504a6-107">藉由指定類型，傳回量子錯誤修正程式碼的執行 `QECC` 。</span><span class="sxs-lookup"><span data-stu-id="504a6-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>