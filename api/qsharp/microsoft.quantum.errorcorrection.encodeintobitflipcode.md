---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: EncodeIntoBitFlipCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697990"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="54e23-102">EncodeIntoBitFlipCode 操作</span><span class="sxs-lookup"><span data-stu-id="54e23-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="54e23-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="54e23-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="54e23-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54e23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54e23-105">編碼為 [3，1，3]/⟦3，1，1⟧位-翻轉程式碼。</span><span class="sxs-lookup"><span data-stu-id="54e23-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="54e23-106">輸入</span><span class="sxs-lookup"><span data-stu-id="54e23-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="54e23-107">physRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="54e23-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="54e23-108">代表要保護之資料的實體量子位註冊。</span><span class="sxs-lookup"><span data-stu-id="54e23-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="54e23-109">auxQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="54e23-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="54e23-110">一開始會在 $ \ket $ 狀態中註冊輔助量子位， {00} 以用於編碼要保護的資料。</span><span class="sxs-lookup"><span data-stu-id="54e23-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="54e23-111">輸出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="54e23-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="54e23-112">用於編碼的實體和輔助量子位，以邏輯暫存器表示。</span><span class="sxs-lookup"><span data-stu-id="54e23-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="54e23-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="54e23-113">See Also</span></span>

- [<span data-ttu-id="54e23-114">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="54e23-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)