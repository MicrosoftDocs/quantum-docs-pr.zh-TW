---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction 使用者定義型別
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846908"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="761d4-102">BigFraction 使用者定義型別</span><span class="sxs-lookup"><span data-stu-id="761d4-102">BigFraction user defined type</span></span>

<span data-ttu-id="761d4-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="761d4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="761d4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="761d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="761d4-105">表示表單的有理數 `p/q` 。</span><span class="sxs-lookup"><span data-stu-id="761d4-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="761d4-106">整數 `p` 是元組的第一個元素，而 `q` 是元組的第二個元素。</span><span class="sxs-lookup"><span data-stu-id="761d4-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="761d4-107">命名專案</span><span class="sxs-lookup"><span data-stu-id="761d4-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="761d4-108">分子： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="761d4-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="761d4-109">分數的分子。</span><span class="sxs-lookup"><span data-stu-id="761d4-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="761d4-110">分母： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="761d4-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="761d4-111">分數/的分母</span><span class="sxs-lookup"><span data-stu-id="761d4-111">Denominator of the fraction/</span></span>