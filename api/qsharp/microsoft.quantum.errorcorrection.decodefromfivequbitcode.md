---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: DecodeFromFiveQubitCode 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 77c5614684f416c7d2e12914ec6246d3ef7098fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201099"
---
# <a name="decodefromfivequbitcode-operation"></a><span data-ttu-id="d8c13-102">DecodeFromFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="d8c13-102">DecodeFromFiveQubitCode operation</span></span>

<span data-ttu-id="d8c13-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d8c13-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d8c13-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8c13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8c13-105">解碼⟦5，1，3⟧量副程式代碼。</span><span class="sxs-lookup"><span data-stu-id="d8c13-105">Decodes the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="d8c13-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d8c13-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="d8c13-107">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="d8c13-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="d8c13-108">量子位的陣列，代表編碼的5量子位程式碼邏輯狀態。</span><span class="sxs-lookup"><span data-stu-id="d8c13-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="d8c13-109">Output： ([量子位](xref:microsoft.quantum.lang-ref.qubit)[]，[量子位](xref:microsoft.quantum.lang-ref.qubit)[] ) </span><span class="sxs-lookup"><span data-stu-id="d8c13-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="d8c13-110">長度為1的量子位陣列，代表第一個參數中未編碼的狀態，以及第二個參數中的輔助量子位。</span><span class="sxs-lookup"><span data-stu-id="d8c13-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8c13-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d8c13-111">See Also</span></span>

- [<span data-ttu-id="d8c13-112">ErrorCorrection. FiveQubitCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="d8c13-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [<span data-ttu-id="d8c13-113">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="d8c13-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)