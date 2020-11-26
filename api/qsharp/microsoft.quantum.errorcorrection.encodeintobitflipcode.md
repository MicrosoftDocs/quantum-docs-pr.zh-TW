---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b27759caba3c5dd363dbdf24d6e5de76870173cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200946"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="3a612-102">EncodeIntoBitFlipCode 操作</span><span class="sxs-lookup"><span data-stu-id="3a612-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="3a612-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3a612-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3a612-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3a612-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3a612-105">編碼為 [3，1，3]/⟦3，1，1⟧位-翻轉程式碼。</span><span class="sxs-lookup"><span data-stu-id="3a612-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="3a612-106">輸入</span><span class="sxs-lookup"><span data-stu-id="3a612-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="3a612-107">physRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3a612-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3a612-108">代表要保護之資料的實體量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="3a612-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="3a612-109">auxQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3a612-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3a612-110">一開始會在 $ \ket $ 狀態中註冊輔助量子位， {00} 以用於編碼要保護的資料。</span><span class="sxs-lookup"><span data-stu-id="3a612-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="3a612-111">輸出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="3a612-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="3a612-112">用於編碼的實體和輔助量子位，以邏輯暫存器表示。</span><span class="sxs-lookup"><span data-stu-id="3a612-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a612-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3a612-113">See Also</span></span>

- [<span data-ttu-id="3a612-114">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="3a612-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)