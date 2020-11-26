---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 0d768114c84025a067e0b60762e6834fbd36deb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228180"
---
# <a name="inversemodl-function"></a><span data-ttu-id="f250d-102">InverseModL 函式</span><span class="sxs-lookup"><span data-stu-id="f250d-102">InverseModL function</span></span>

<span data-ttu-id="f250d-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f250d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f250d-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f250d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f250d-105">傳回 $b $，$a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="f250d-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="f250d-106">輸入</span><span class="sxs-lookup"><span data-stu-id="f250d-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f250d-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f250d-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f250d-108">要反轉的數位</span><span class="sxs-lookup"><span data-stu-id="f250d-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="f250d-109">模數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f250d-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f250d-110">根據數位反轉的模數</span><span class="sxs-lookup"><span data-stu-id="f250d-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="f250d-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f250d-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f250d-112">整數 $b $，例如 $a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="f250d-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>