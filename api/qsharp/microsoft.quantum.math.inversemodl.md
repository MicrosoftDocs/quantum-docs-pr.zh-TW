---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700611"
---
# <a name="inversemodl-function"></a><span data-ttu-id="1949f-102">InverseModL 函式</span><span class="sxs-lookup"><span data-stu-id="1949f-102">InverseModL function</span></span>

<span data-ttu-id="1949f-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1949f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1949f-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1949f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1949f-105">傳回 $b $，$a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="1949f-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="1949f-106">輸入</span><span class="sxs-lookup"><span data-stu-id="1949f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1949f-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1949f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1949f-108">要反轉的數位</span><span class="sxs-lookup"><span data-stu-id="1949f-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="1949f-109">模數： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1949f-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1949f-110">根據數位反轉的模數</span><span class="sxs-lookup"><span data-stu-id="1949f-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1949f-111">輸出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1949f-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1949f-112">整數 $b $，例如 $a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="1949f-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>