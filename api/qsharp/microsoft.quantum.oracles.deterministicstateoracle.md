---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842583"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="1b50d-102">DeterministicStateOracle 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="1b50d-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="1b50d-103">命名空間： [oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="1b50d-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="1b50d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b50d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b50d-105">表示 oracle for 決定性狀態準備。</span><span class="sxs-lookup"><span data-stu-id="1b50d-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="1b50d-106">Oracle $O $ 的輸入為：</span><span class="sxs-lookup"><span data-stu-id="1b50d-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="1b50d-107">將儲存所需量子狀態 $ \ket{\psi} \_ s $ 的註冊。</span><span class="sxs-lookup"><span data-stu-id="1b50d-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="1b50d-108">備註</span><span class="sxs-lookup"><span data-stu-id="1b50d-108">Remarks</span></span>

<span data-ttu-id="1b50d-109">由 $O \ket = \ket{\psi} $ 定義的 oracle 會 {0} 在 on 計算基礎狀態 $ \ket $ 上採取動作 {0} ，以建立狀態 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="1b50d-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="1b50d-110">第一個參數是 $ \ket{\psi} $ 的量子位暫存器。</span><span class="sxs-lookup"><span data-stu-id="1b50d-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>