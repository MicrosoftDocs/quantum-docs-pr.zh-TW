---
uid: Microsoft.Quantum.Simulation.TimeDependentBlockEncoding
title: TimeDependentBlockEncoding 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentBlockEncoding
qsharp.summary: >-
  Represents a `BlockEncoding` that is controlled by a clock register.

  That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k. \end{align} $$.
ms.openlocfilehash: e2b191a4fc44f99c88f25da9b1ee6460d936740b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814272"
---
# <a name="timedependentblockencoding-user-defined-type"></a><span data-ttu-id="03e68-102">TimeDependentBlockEncoding 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="03e68-102">TimeDependentBlockEncoding user defined type</span></span>

<span data-ttu-id="03e68-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="03e68-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="03e68-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03e68-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03e68-105">表示由時鐘暫存器所 `BlockEncoding` 控制的。</span><span class="sxs-lookup"><span data-stu-id="03e68-105">Represents a `BlockEncoding` that is controlled by a clock register.</span></span>

<span data-ttu-id="03e68-106">也就是說，a `TimeDependentBlockEncoding` 是由 state $ \ket{k} _d $ in clock register 所控制的單一 $U $，如此一來，在系統暫存器 `d` 上作用的任意運算子 $H _k $， `s` 會在對應至輔助狀態 $ \ket _a $ 的左上角區塊中進行編碼 {0} 。</span><span class="sxs-lookup"><span data-stu-id="03e68-106">That is, a `TimeDependentBlockEncoding` is a unitary $U$ controlled by a state $\ket{k}_d$ in clock register `d` such that an arbitrary operator $H_k$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="03e68-107">那是</span><span class="sxs-lookup"><span data-stu-id="03e68-107">That is,</span></span>

<span data-ttu-id="03e68-108">$ $ \begin{align} ( \bra {0} \_ a\otimes I_ {ds} ) U ( \ket {0} \_ a\otimes I_ {ds} ) = \ sum_ {k} \ket{k}\bra{k} \_ d\otimes H_k。</span><span class="sxs-lookup"><span data-stu-id="03e68-108">$$ \begin{align} (\bra{0}\_a\otimes I_{ds})U(\ket{0}\_a\otimes I_{ds}) = \sum_{k}\ket{k}\bra{k}\_d\otimes H_k.</span></span>
<span data-ttu-id="03e68-109">\end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="03e68-109">\end{align} $$.</span></span>

```qsharp

newtype TimeDependentBlockEncoding = (((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

