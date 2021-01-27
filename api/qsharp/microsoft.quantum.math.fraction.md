---
uid: Microsoft.Quantum.Math.Fraction
title: 分數使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857506"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="5e0f5-102">分數使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="5e0f5-102">Fraction user defined type</span></span>

<span data-ttu-id="5e0f5-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5e0f5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5e0f5-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e0f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e0f5-105">表示表單的有理數 `p/q` 。</span><span class="sxs-lookup"><span data-stu-id="5e0f5-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="5e0f5-106">整數 `p` 是元組的第一個元素，而 `q` 是元組的第二個元素。</span><span class="sxs-lookup"><span data-stu-id="5e0f5-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="5e0f5-107">命名專案</span><span class="sxs-lookup"><span data-stu-id="5e0f5-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="5e0f5-108">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e0f5-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e0f5-109">分數的分子。</span><span class="sxs-lookup"><span data-stu-id="5e0f5-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="5e0f5-110">分母： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e0f5-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e0f5-111">分數/的分母</span><span class="sxs-lookup"><span data-stu-id="5e0f5-111">Denominator of the fraction/</span></span>