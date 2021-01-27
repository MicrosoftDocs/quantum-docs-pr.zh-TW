---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842932"
---
# <a name="squaresi-operation"></a><span data-ttu-id="465cd-102">SquareSI 操作</span><span class="sxs-lookup"><span data-stu-id="465cd-102">SquareSI operation</span></span>

<span data-ttu-id="465cd-103">命名空間： [Microsoft 量子](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="465cd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="465cd-104">封裝： [Microsoft 量子. 數值](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="465cd-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="465cd-105">以方形帶正負號 `xs` 的整數，並將結果儲存在中 `result` ，這一開始必須是零。</span><span class="sxs-lookup"><span data-stu-id="465cd-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="465cd-106">輸入</span><span class="sxs-lookup"><span data-stu-id="465cd-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="465cd-107">xs： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="465cd-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="465cd-108">n 位整數至平方 (SignedLittleEndian) </span><span class="sxs-lookup"><span data-stu-id="465cd-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="465cd-109">結果： [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="465cd-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="465cd-110">2n 位結果 (SignedLittleEndian) ，必須先處於 state $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="465cd-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="465cd-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="465cd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="465cd-112">備註</span><span class="sxs-lookup"><span data-stu-id="465cd-112">Remarks</span></span>

<span data-ttu-id="465cd-113">此執行依賴 IntegerSquare。</span><span class="sxs-lookup"><span data-stu-id="465cd-113">The implementation relies on IntegerSquare.</span></span>