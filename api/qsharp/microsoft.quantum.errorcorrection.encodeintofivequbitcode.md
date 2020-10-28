---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: EncodeIntoFiveQubitCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: c9df4c5c98a78cae8b3af4597020d35469454153
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697987"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="603f3-102">EncodeIntoFiveQubitCode 操作</span><span class="sxs-lookup"><span data-stu-id="603f3-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="603f3-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="603f3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="603f3-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="603f3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="603f3-105">編碼為⟦5，1，3⟧量副程式代碼。</span><span class="sxs-lookup"><span data-stu-id="603f3-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="603f3-106">輸入</span><span class="sxs-lookup"><span data-stu-id="603f3-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="603f3-107">physRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="603f3-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="603f3-108">量子位，代表未編碼的狀態。</span><span class="sxs-lookup"><span data-stu-id="603f3-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="603f3-109">這個陣列 `Qubit[]` 的長度為1。</span><span class="sxs-lookup"><span data-stu-id="603f3-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="603f3-110">auxQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="603f3-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="603f3-111">將用來表示已編碼狀態的輔助量子位的註冊。</span><span class="sxs-lookup"><span data-stu-id="603f3-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="603f3-112">輸出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="603f3-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="603f3-113">儲存編碼狀態之類型的實體量子位陣列 `LogicalRegister` 。</span><span class="sxs-lookup"><span data-stu-id="603f3-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="603f3-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="603f3-114">See Also</span></span>

- [<span data-ttu-id="603f3-115">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="603f3-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)