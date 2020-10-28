---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 5b8afe222d197eb7d342ac45f027f2de9130b61a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697967"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="caa92-102">FiveQubitCodeRecoveryFn 函式</span><span class="sxs-lookup"><span data-stu-id="caa92-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="caa92-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="caa92-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="caa92-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="caa92-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="caa92-105">傳回函式，此函式會將錯誤的症狀度量對應至⟦5，1，3⟧量副程式代碼的資料表查閱適當的錯誤更正 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="caa92-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="caa92-106">輸出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="caa92-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="caa92-107">型別為 `RecoveryFn` 的函式，它會接受發生症狀測量 `Result[]` ，並傳回 `Pauli[]` 可更正偵測到之錯誤的運算子。</span><span class="sxs-lookup"><span data-stu-id="caa92-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="caa92-108">備註</span><span class="sxs-lookup"><span data-stu-id="caa92-108">Remarks</span></span>

<span data-ttu-id="caa92-109">藉由逐一查看權數 $1 $ 的所有錯誤，我們總共取得了 $ 3 \ 乘以 5 = 15 $ 的非一般 syndromes。</span><span class="sxs-lookup"><span data-stu-id="caa92-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="caa92-110">與身分識別一起，會建立錯誤資料表和對應的症狀。</span><span class="sxs-lookup"><span data-stu-id="caa92-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="caa92-111">在5個量子位程式碼中，此資料表是由所提供： $X \_ 1： (0、0、0、1) ;X \_ 2： (1、0、0、0) ;X \_ 3： (1、1、0、0) ;X \_ 4： (0、1、1、0) ;X \_ 5： (0、0、1、1) $、$Z \_ 1： (1、0、1、0) ;Z \_ 2： (0、1、0、1) ;Z \_ 3： (0、0、1、0) ;Z \_ 4： (1、0、0、1) ;Z \_ 5： (0、1、0、0) $，$Y _i $，方法是新增 $X _i $ 和 $Z _i $ syndromes。</span><span class="sxs-lookup"><span data-stu-id="caa92-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="caa92-112">請注意，資料表查閱復原中的順序是藉由將 bitvectors 轉換為整數 (使用位元組由小到大的) 來提供。</span><span class="sxs-lookup"><span data-stu-id="caa92-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="caa92-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="caa92-113">See Also</span></span>

- [<span data-ttu-id="caa92-114">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="caa92-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)