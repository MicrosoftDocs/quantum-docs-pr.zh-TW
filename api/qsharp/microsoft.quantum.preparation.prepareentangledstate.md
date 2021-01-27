---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854372"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="2728c-102">PrepareEntangledState 操作</span><span class="sxs-lookup"><span data-stu-id="2728c-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="2728c-103">命名空間： [Microsoft 量子. 準備](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2728c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2728c-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2728c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2728c-105">成對 entangles 兩個量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="2728c-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="2728c-106">亦即，假設有兩個暫存器，請在個別暫存器上的每一對 \left 之間準備充分纏結 state $ \frac {1} {\sqrt {2} } \ket ( \ket {00} + \right {11} 量子位) $，假設每個暫存器都是以 $ \ket{0\cdots 0} $ 狀態開始。</span><span class="sxs-lookup"><span data-stu-id="2728c-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2728c-107">輸入</span><span class="sxs-lookup"><span data-stu-id="2728c-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="2728c-108">左方： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2728c-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2728c-109">$ \Ket{0\cdots 0} $ 狀態中的量子位陣列</span><span class="sxs-lookup"><span data-stu-id="2728c-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="2728c-110">right： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2728c-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2728c-111">$ \Ket{0\cdots 0} $ 狀態中的量子位陣列</span><span class="sxs-lookup"><span data-stu-id="2728c-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="2728c-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2728c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

