---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841581"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="1779d-102">ApplyPauliFromBitString 操作</span><span class="sxs-lookup"><span data-stu-id="1779d-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="1779d-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1779d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1779d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1779d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1779d-105">如果布林值陣列的對應位符合指定的輸入，則在陣列中的每個量子位上套用 Pauli 運算子。</span><span class="sxs-lookup"><span data-stu-id="1779d-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1779d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1779d-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="1779d-107">pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="1779d-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="1779d-108">要套用至 `qubits[idx]` where 的 Pauli 運算子 `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="1779d-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="1779d-109">bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1779d-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1779d-110">如果位為此值，則套用 Pauli</span><span class="sxs-lookup"><span data-stu-id="1779d-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="1779d-111">位： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1779d-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1779d-112">布林值暫存器，指定應操作的對應量子位 `qubits`</span><span class="sxs-lookup"><span data-stu-id="1779d-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="1779d-113">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1779d-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1779d-114">要選擇性地套用指定 Pauli 操作員的量子暫存器</span><span class="sxs-lookup"><span data-stu-id="1779d-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="1779d-115">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1779d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1779d-116">備註</span><span class="sxs-lookup"><span data-stu-id="1779d-116">Remarks</span></span>

<span data-ttu-id="1779d-117">布林陣列和量子暫存器的長度必須相等。</span><span class="sxs-lookup"><span data-stu-id="1779d-117">The Boolean array and the quantum register must be of equal length.</span></span>