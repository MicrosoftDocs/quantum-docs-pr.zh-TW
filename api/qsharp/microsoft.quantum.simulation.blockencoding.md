---
uid: Microsoft.Quantum.Simulation.BlockEncoding
title: BlockEncoding 使用者定義型別
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncoding
qsharp.summary: >-
  Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.

  That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$. That is,

  $$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.
ms.openlocfilehash: 1b769c58fd23b4ebc9d779cec3c47d8275822e5a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700343"
---
# <a name="blockencoding-user-defined-type"></a><span data-ttu-id="1f8d2-102">BlockEncoding 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="1f8d2-102">BlockEncoding user defined type</span></span>

<span data-ttu-id="1f8d2-103">命名空間： [Microsoft 量子. 模擬](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1f8d2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1f8d2-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f8d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f8d2-105">表示在左上角區塊中編碼任意運算子的單一位置。</span><span class="sxs-lookup"><span data-stu-id="1f8d2-105">Represents a unitary where an arbitrary operator of interest is encoded in the top-left block.</span></span>

<span data-ttu-id="1f8d2-106">亦即，a `BlockEncoding` 是一個單一 $U $，在系統暫存器上作用的任意運算子 $H $， `s` 會在對應至輔助狀態 $ \ket _a $ 的左上角區塊中進行編碼 {0} 。</span><span class="sxs-lookup"><span data-stu-id="1f8d2-106">That is, a `BlockEncoding` is a unitary $U$ where an arbitrary operator $H$ of interest that acts on the system register `s` is encoded in the top- left block corresponding to auxiliary state $\ket{0}_a$.</span></span> <span data-ttu-id="1f8d2-107">那是</span><span class="sxs-lookup"><span data-stu-id="1f8d2-107">That is,</span></span>

<span data-ttu-id="1f8d2-108">$ $ \begin{align} ( \bra {0} _a \otimes I_s) U ( \ket {0} _a \otimes I_s) = H \end{align} $ $。</span><span class="sxs-lookup"><span data-stu-id="1f8d2-108">$$ \begin{align} (\bra{0}_a\otimes I_s)U(\ket{0}_a\otimes I_s) = H \end{align} $$.</span></span>

```qsharp

newtype BlockEncoding = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```

