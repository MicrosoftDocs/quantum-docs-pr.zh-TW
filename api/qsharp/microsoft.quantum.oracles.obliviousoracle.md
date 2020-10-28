---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 7c5b35984f3c8828a5ba9bdae8f9effbc1d378f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697586"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="83ed7-102">ObliviousOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="83ed7-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="83ed7-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="83ed7-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="83ed7-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83ed7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83ed7-105">表示 oracle for 無警示振幅放大。</span><span class="sxs-lookup"><span data-stu-id="83ed7-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="83ed7-106">Oracle $O $ 的輸入包括：</span><span class="sxs-lookup"><span data-stu-id="83ed7-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="83ed7-107">$O $ 作用的 ancilla 暫存器 $a $。</span><span class="sxs-lookup"><span data-stu-id="83ed7-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="83ed7-108">系統註冊 $s $ （要套用所需的單一 $U $），在 register $a $ \ket{t} a $ 的 post 選取 \_ 。</span><span class="sxs-lookup"><span data-stu-id="83ed7-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="83ed7-109">備註</span><span class="sxs-lookup"><span data-stu-id="83ed7-109">Remarks</span></span>

<span data-ttu-id="83ed7-110">此 oracle 由 $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ 作用於 ancilla state $ \ket{s} \_ a $，以 \_ $ \ket{\psi} a $ 的基礎，以振幅 $ \lambda $ 來執行任何系統狀態 $ \ket{t} s $ 上的單一 $U $ \_ 。</span><span class="sxs-lookup"><span data-stu-id="83ed7-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="83ed7-111">第一個參數是 $ \ket{s} a $ 的量子位暫存器 \_ 。</span><span class="sxs-lookup"><span data-stu-id="83ed7-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="83ed7-112">第二個參數是 $ \ket{\psi} s $ 的量子位暫存器 \_ 。</span><span class="sxs-lookup"><span data-stu-id="83ed7-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>