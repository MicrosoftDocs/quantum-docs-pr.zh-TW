---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223930"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="0bf74-102">_prepareEntangledState 操作</span><span class="sxs-lookup"><span data-stu-id="0bf74-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="0bf74-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0bf74-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0bf74-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0bf74-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0bf74-105">假設有兩個暫存器，請在個別暫存器上的每一對量子位之間準備充分纏結狀態。</span><span class="sxs-lookup"><span data-stu-id="0bf74-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="0bf74-106">所有量子位都必須以 | 0 ⟩狀態開始。</span><span class="sxs-lookup"><span data-stu-id="0bf74-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="0bf74-107">結果是，每個註冊程式的對應量子位都位於 $ \bra{\ Beta_ {00} } \ket{\ Beta_ {00} } $。</span><span class="sxs-lookup"><span data-stu-id="0bf74-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0bf74-108">輸入</span><span class="sxs-lookup"><span data-stu-id="0bf74-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="0bf74-109">左方： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0bf74-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0bf74-110">$ \Ket{0\cdots 0} $ 狀態中的量子位陣列</span><span class="sxs-lookup"><span data-stu-id="0bf74-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="0bf74-111">right： [量子位](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0bf74-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0bf74-112">$ \Ket{0\cdots 0} $ 狀態中的量子位陣列</span><span class="sxs-lookup"><span data-stu-id="0bf74-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="0bf74-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0bf74-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

