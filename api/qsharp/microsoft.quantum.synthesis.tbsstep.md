---
uid: Microsoft.Quantum.Synthesis.TBSStep
title: TBSStep 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TBSStep
qsharp.summary: Computes gate masks to transform perm[x] to x and updates the current permutation.
ms.openlocfilehash: b33269afc2ac14106a18a09e855a8d067b9c558b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701131"
---
# <a name="tbsstep-function"></a><span data-ttu-id="f659b-102">TBSStep 函式</span><span class="sxs-lookup"><span data-stu-id="f659b-102">TBSStep function</span></span>

<span data-ttu-id="f659b-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f659b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f659b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f659b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f659b-105">計算用來將為永久 [x] 轉換為 x 的閘道遮罩，並更新目前的排列。</span><span class="sxs-lookup"><span data-stu-id="f659b-105">Computes gate masks to transform perm[x] to x and updates the current permutation.</span></span>

```qsharp
function TBSStep (state : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[]), x : Int) : (Int[], Microsoft.Quantum.Synthesis.MCMTMask[])
```


## <a name="input"></a><span data-ttu-id="f659b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f659b-106">Input</span></span>

### <a name="state--intmcmtmask"></a><span data-ttu-id="f659b-107">狀態： ([Int](xref:microsoft.quantum.lang-ref.int)[]，[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[] ) </span><span class="sxs-lookup"><span data-stu-id="f659b-107">state : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>




### <a name="x--int"></a><span data-ttu-id="f659b-108">x： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f659b-108">x : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intmcmtmask"></a><span data-ttu-id="f659b-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)[]，[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[] ) </span><span class="sxs-lookup"><span data-stu-id="f659b-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int)[],[MCMTMask](xref:Microsoft.Quantum.Synthesis.MCMTMask)[])</span></span>

