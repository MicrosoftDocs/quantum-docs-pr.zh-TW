---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697914"
---
# <a name="steanecoderecoveryfns-function"></a><span data-ttu-id="fef9b-102">SteaneCodeRecoveryFns 函式</span><span class="sxs-lookup"><span data-stu-id="fef9b-102">SteaneCodeRecoveryFns function</span></span>

<span data-ttu-id="fef9b-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="fef9b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="fef9b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fef9b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fef9b-105">適用于⟦7，1，3⟧ Steane 量副程式代碼之穩定型別的 X 和 Z 部分組合的解碼器。</span><span class="sxs-lookup"><span data-stu-id="fef9b-105">Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a><span data-ttu-id="fef9b-106">Output： ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)，[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)) </span><span class="sxs-lookup"><span data-stu-id="fef9b-106">Output : ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span></span>

<span data-ttu-id="fef9b-107">型別函式的元組 `RecoveryFn` ，會採取症狀測量 `Result[]` ，並傳回 `Pauli[]` 可更正偵測到之錯誤的作業。</span><span class="sxs-lookup"><span data-stu-id="fef9b-107">Tuple of functions of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="fef9b-108">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fef9b-108">See Also</span></span>

- [<span data-ttu-id="fef9b-109">ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="fef9b-109">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="fef9b-110">ErrorCorrection. SteaneCodeRecoveryZ</span><span class="sxs-lookup"><span data-stu-id="fef9b-110">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)