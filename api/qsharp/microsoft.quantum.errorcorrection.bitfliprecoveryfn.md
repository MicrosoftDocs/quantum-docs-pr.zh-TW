---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698015"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="c3b6f-102">BitFlipRecoveryFn 函式</span><span class="sxs-lookup"><span data-stu-id="c3b6f-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="c3b6f-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c3b6f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c3b6f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3b6f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3b6f-105">針對⟦3，1，1⟧位翻轉程式碼的資料表查閱，針對指定的 Pauli 作業進行的復原作業函數。</span><span class="sxs-lookup"><span data-stu-id="c3b6f-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="c3b6f-106">輸出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="c3b6f-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="c3b6f-107">型別為 `RecoveryFn` 的函式，它會接受發生症狀測量 `Result[]` ，並傳回 `Pauli[]` 可更正偵測到之錯誤的作業。</span><span class="sxs-lookup"><span data-stu-id="c3b6f-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3b6f-108">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c3b6f-108">See Also</span></span>

- [<span data-ttu-id="c3b6f-109">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="c3b6f-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)