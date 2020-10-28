---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701055"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="665cd-102">FastHadamardTransformed 函式</span><span class="sxs-lookup"><span data-stu-id="665cd-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="665cd-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="665cd-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="665cd-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="665cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="665cd-105">{-1,1}使用 Yates 的方法，以編碼方式計算布耳函數的 Hadamard 轉換</span><span class="sxs-lookup"><span data-stu-id="665cd-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="665cd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="665cd-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="665cd-107">func： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="665cd-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="665cd-108">編碼中的事實資料表 {-1,1}</span><span class="sxs-lookup"><span data-stu-id="665cd-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="665cd-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="665cd-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="665cd-110">函數的光譜系數</span><span class="sxs-lookup"><span data-stu-id="665cd-110">Spectral coefficients of the function</span></span>