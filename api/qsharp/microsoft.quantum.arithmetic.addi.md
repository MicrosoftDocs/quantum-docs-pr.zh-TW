---
uid: Microsoft.Quantum.Arithmetic.AddI
title: AddI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843855"
---
# <a name="addi-operation"></a><span data-ttu-id="7153b-102">AddI 操作</span><span class="sxs-lookup"><span data-stu-id="7153b-102">AddI operation</span></span>

<span data-ttu-id="7153b-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7153b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7153b-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7153b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7153b-105">視的註冊大小而定，自動選擇 [包含] 或 [無] `ys` 。</span><span class="sxs-lookup"><span data-stu-id="7153b-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7153b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="7153b-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="7153b-107">xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7153b-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7153b-108">$n $ bit 加數。</span><span class="sxs-lookup"><span data-stu-id="7153b-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="7153b-109">y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7153b-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7153b-110">至少有 $n $ 量子位的加數。</span><span class="sxs-lookup"><span data-stu-id="7153b-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="7153b-111">將會保留結果。</span><span class="sxs-lookup"><span data-stu-id="7153b-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7153b-112">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7153b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

