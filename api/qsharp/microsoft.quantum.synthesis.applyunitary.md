---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859134"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="57fb8-102">ApplyUnitary 操作</span><span class="sxs-lookup"><span data-stu-id="57fb8-102">ApplyUnitary operation</span></span>

<span data-ttu-id="57fb8-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="57fb8-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="57fb8-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57fb8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57fb8-105">套用 2 ^ n x 2 ^ n 個單一矩陣所定義的閘道。</span><span class="sxs-lookup"><span data-stu-id="57fb8-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="57fb8-106">如果矩陣不是單一或大小錯誤，則會失敗。</span><span class="sxs-lookup"><span data-stu-id="57fb8-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="57fb8-107">輸入</span><span class="sxs-lookup"><span data-stu-id="57fb8-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="57fb8-108">單一： [複雜](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="57fb8-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="57fb8-109">描述作業的 2 ^ n x 2 ^ n 個單一矩陣。</span><span class="sxs-lookup"><span data-stu-id="57fb8-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="57fb8-110">如果矩陣不是單一或不適合的大小，則會擲回例外狀況。</span><span class="sxs-lookup"><span data-stu-id="57fb8-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="57fb8-111">量子位： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="57fb8-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="57fb8-112">套用作業的量子位（長度為 n 的註冊）。</span><span class="sxs-lookup"><span data-stu-id="57fb8-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57fb8-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57fb8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

