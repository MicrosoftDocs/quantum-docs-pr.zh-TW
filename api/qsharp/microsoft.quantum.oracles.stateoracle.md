---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854475"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="912ec-102">StateOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="912ec-102">StateOracle user defined type</span></span>

<span data-ttu-id="912ec-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="912ec-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="912ec-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="912ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="912ec-105">代表 oracle 的狀態準備。</span><span class="sxs-lookup"><span data-stu-id="912ec-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="912ec-106">Oracle $O $ 的輸入包括：</span><span class="sxs-lookup"><span data-stu-id="912ec-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="912ec-107">將旗標量子位 $f $ 索引的整數。</span><span class="sxs-lookup"><span data-stu-id="912ec-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="912ec-108">系統註冊 $s $，將會儲存所需的量子狀態 $ \ket{\psi} \_ s $。</span><span class="sxs-lookup"><span data-stu-id="912ec-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="912ec-109">備註</span><span class="sxs-lookup"><span data-stu-id="912ec-109">Remarks</span></span>

<span data-ttu-id="912ec-110">此 oracle 由 $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots 所定義，$ $ 作用於 on 計算基礎狀態 $ \ket {0} \_ {f} \ket {0} \_ s $，以 \_ $ \ket{\psi} {1} f $ 標示的基礎，以振幅 $ \lambda $ 來建立目標狀態 $ \ket s $ \_ 。</span><span class="sxs-lookup"><span data-stu-id="912ec-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="912ec-111">第一個參數是 $ \ket f $ 的量子位暫存器的索引 {0} \_ 。</span><span class="sxs-lookup"><span data-stu-id="912ec-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="912ec-112">第二個參數包含這兩個暫存器。</span><span class="sxs-lookup"><span data-stu-id="912ec-112">The second parameter encompassed both registers.</span></span>