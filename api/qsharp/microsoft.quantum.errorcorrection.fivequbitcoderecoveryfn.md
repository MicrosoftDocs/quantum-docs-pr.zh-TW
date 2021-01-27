---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853133"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="91de7-102">FiveQubitCodeRecoveryFn 函式</span><span class="sxs-lookup"><span data-stu-id="91de7-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="91de7-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="91de7-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="91de7-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91de7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91de7-105">傳回函式，此函式會將錯誤的症狀度量對應至⟦5，1，3⟧量副程式代碼的資料表查閱適當的錯誤更正 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="91de7-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="91de7-106">輸出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="91de7-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="91de7-107">型別為 `RecoveryFn` 的函式，它會接受發生症狀測量 `Result[]` ，並傳回 `Pauli[]` 可更正偵測到之錯誤的運算子。</span><span class="sxs-lookup"><span data-stu-id="91de7-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="91de7-108">備註</span><span class="sxs-lookup"><span data-stu-id="91de7-108">Remarks</span></span>

<span data-ttu-id="91de7-109">藉由逐一查看權數 $1 $ 的所有錯誤，我們總共取得了 $ 3 \ 乘以 5 = 15 $ 的非一般 syndromes。</span><span class="sxs-lookup"><span data-stu-id="91de7-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="91de7-110">與身分識別一起，會建立錯誤資料表和對應的症狀。</span><span class="sxs-lookup"><span data-stu-id="91de7-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="91de7-111">在5個量子位程式碼中，此資料表是由所提供： $X \_ 1： (0、0、0、1) ;X \_ 2： (1、0、0、0) ;X \_ 3： (1、1、0、0) ;X \_ 4： (0、1、1、0) ;X \_ 5： (0、0、1、1) $、$Z \_ 1： (1、0、1、0) ;Z \_ 2： (0、1、0、1) ;Z \_ 3： (0、0、1、0) ;Z \_ 4： (1、0、0、1) ;Z \_ 5： (0、1、0、0) $，$Y _i $，方法是新增 $X _i $ 和 $Z _i $ syndromes。</span><span class="sxs-lookup"><span data-stu-id="91de7-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="91de7-112">請注意，資料表查閱復原中的順序是藉由將 bitvectors 轉換為整數 (使用位元組由小到大的) 來提供。</span><span class="sxs-lookup"><span data-stu-id="91de7-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="91de7-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="91de7-113">See Also</span></span>

- [<span data-ttu-id="91de7-114">ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="91de7-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)