---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: DecodeFromBitFlipCode 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 84cf83f24d02f261f1768e16390f83c9b294b759
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201150"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="dfb10-102">DecodeFromBitFlipCode 操作</span><span class="sxs-lookup"><span data-stu-id="dfb10-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="dfb10-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="dfb10-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="dfb10-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dfb10-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dfb10-105">從 [3，1，3]/⟦3，1，1⟧位翻轉程式碼解碼。</span><span class="sxs-lookup"><span data-stu-id="dfb10-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="dfb10-106">輸入</span><span class="sxs-lookup"><span data-stu-id="dfb10-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="dfb10-107">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="dfb10-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="dfb10-108">位翻轉程式碼的程式碼區塊。</span><span class="sxs-lookup"><span data-stu-id="dfb10-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="dfb10-109">Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) </span><span class="sxs-lookup"><span data-stu-id="dfb10-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="dfb10-110">編碼為邏輯暫存器之資料的元組，以及用來代表症狀的輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="dfb10-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="dfb10-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dfb10-111">See Also</span></span>

- [<span data-ttu-id="dfb10-112">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="dfb10-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="dfb10-113">ErrorCorrection. EncodeIntoBitFlipCode</span><span class="sxs-lookup"><span data-stu-id="dfb10-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)