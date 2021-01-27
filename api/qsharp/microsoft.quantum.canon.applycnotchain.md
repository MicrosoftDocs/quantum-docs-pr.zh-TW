---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: b5a74eb66529095233c89a4ec7ea37c996458cb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841953"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="3763f-102">ApplyCNOTChain 操作</span><span class="sxs-lookup"><span data-stu-id="3763f-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="3763f-103">命名空間： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3763f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3763f-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3763f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3763f-105">計算就地登錄量子位的同位檢查。</span><span class="sxs-lookup"><span data-stu-id="3763f-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="3763f-106">描述</span><span class="sxs-lookup"><span data-stu-id="3763f-106">Description</span></span>

<span data-ttu-id="3763f-107">這項作業會將其輸入的狀態轉換為 $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1-1}}。</span><span class="sxs-lookup"><span data-stu-id="3763f-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="3763f-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3763f-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="3763f-109">輸入</span><span class="sxs-lookup"><span data-stu-id="3763f-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="3763f-110">量子位： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3763f-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3763f-111">要計算和儲存其同位檢查的量子位陣列。</span><span class="sxs-lookup"><span data-stu-id="3763f-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3763f-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3763f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

