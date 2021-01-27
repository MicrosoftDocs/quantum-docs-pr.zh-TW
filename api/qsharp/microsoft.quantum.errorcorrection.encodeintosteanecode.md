---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826197"
---
# <a name="encodeintosteanecode-operation"></a><span data-ttu-id="6054f-102">EncodeIntoSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="6054f-102">EncodeIntoSteaneCode operation</span></span>

<span data-ttu-id="6054f-103">命名空間： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="6054f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="6054f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6054f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6054f-105">一種編碼作業，會將未編碼的量子暫存器對應至⟦7、1、3⟧ Steane 量副程式代碼底下的編碼量子暫存器。</span><span class="sxs-lookup"><span data-stu-id="6054f-105">An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="6054f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6054f-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="6054f-107">physRegister： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6054f-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6054f-108">保存未編碼之量子狀態的量子位暫存器</span><span class="sxs-lookup"><span data-stu-id="6054f-108">A qubit register which holds the an unencoded quantum state</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="6054f-109">auxQubits： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6054f-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6054f-110">量子位暫存器，其一開始是零，並會新增至量子系統，以便執行編碼作業</span><span class="sxs-lookup"><span data-stu-id="6054f-110">A qubit register which is initially zero and which gets added to the quantum system so that an encoding operation can be performed</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="6054f-111">輸出： [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="6054f-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="6054f-112">在套用 Steane 編碼器之後保留狀態的量子註冊程式</span><span class="sxs-lookup"><span data-stu-id="6054f-112">A quantum register holding the state after the Steane encoder has been applied</span></span>

## <a name="see-also"></a><span data-ttu-id="6054f-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6054f-113">See Also</span></span>

- [<span data-ttu-id="6054f-114">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="6054f-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="6054f-115">ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="6054f-115">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)