---
uid: Microsoft.Quantum.Arithmetic.Invert2sSI
title: Invert2sSI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Invert2sSI
qsharp.summary: Inverts a given integer modulo 2's complement.
ms.openlocfilehash: 86d90fc5406089549de0036fcaebd9dc9d188c40
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222842"
---
# <a name="invert2ssi-operation"></a><span data-ttu-id="1da5b-102">Invert2sSI 操作</span><span class="sxs-lookup"><span data-stu-id="1da5b-102">Invert2sSI operation</span></span>

<span data-ttu-id="1da5b-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1da5b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1da5b-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="1da5b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="1da5b-105">反轉指定的整數模數2的補數。</span><span class="sxs-lookup"><span data-stu-id="1da5b-105">Inverts a given integer modulo 2's complement.</span></span>

```qsharp
operation Invert2sSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1da5b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1da5b-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="1da5b-107">xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1da5b-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="1da5b-108">n 位帶正負號的整數 (SignedLittleEndian) ，將會反轉模數2的補數。</span><span class="sxs-lookup"><span data-stu-id="1da5b-108">n-bit signed integer (SignedLittleEndian), will be inverted modulo 2's complement.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1da5b-109">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1da5b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

