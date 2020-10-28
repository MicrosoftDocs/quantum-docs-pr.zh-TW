---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699532"
---
# <a name="squaresi-operation"></a><span data-ttu-id="6dd3b-102">SquareSI 操作</span><span class="sxs-lookup"><span data-stu-id="6dd3b-102">SquareSI operation</span></span>

<span data-ttu-id="6dd3b-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6dd3b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6dd3b-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6dd3b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6dd3b-105">以方形帶正負號 `xs` 的整數，並將結果儲存在中 `result` ，這一開始必須是零。</span><span class="sxs-lookup"><span data-stu-id="6dd3b-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6dd3b-106">輸入</span><span class="sxs-lookup"><span data-stu-id="6dd3b-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="6dd3b-107">xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6dd3b-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="6dd3b-108">n 位整數至平方 (SignedLittleEndian) </span><span class="sxs-lookup"><span data-stu-id="6dd3b-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="6dd3b-109">結果： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6dd3b-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="6dd3b-110">2n 位結果 (SignedLittleEndian) ，必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="6dd3b-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6dd3b-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6dd3b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6dd3b-112">備註</span><span class="sxs-lookup"><span data-stu-id="6dd3b-112">Remarks</span></span>

<span data-ttu-id="6dd3b-113">此執行依賴 IntegerSquare。</span><span class="sxs-lookup"><span data-stu-id="6dd3b-113">The implementation relies on IntegerSquare.</span></span>