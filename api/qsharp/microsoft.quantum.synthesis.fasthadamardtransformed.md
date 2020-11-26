---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: FastHadamardTransformed 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203088"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="ecfe1-102">FastHadamardTransformed 函式</span><span class="sxs-lookup"><span data-stu-id="ecfe1-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="ecfe1-103">命名空間： [Microsoft. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ecfe1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ecfe1-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ecfe1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ecfe1-105">{-1,1}使用 Yates 的方法，以編碼方式計算布耳函數的 Hadamard 轉換</span><span class="sxs-lookup"><span data-stu-id="ecfe1-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="ecfe1-106">輸入</span><span class="sxs-lookup"><span data-stu-id="ecfe1-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="ecfe1-107">func： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ecfe1-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ecfe1-108">編碼中的事實資料表 {-1,1}</span><span class="sxs-lookup"><span data-stu-id="ecfe1-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="ecfe1-109">輸出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ecfe1-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ecfe1-110">函數的光譜系數</span><span class="sxs-lookup"><span data-stu-id="ecfe1-110">Spectral coefficients of the function</span></span>