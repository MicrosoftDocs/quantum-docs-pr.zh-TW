---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700614"
---
# <a name="inversemodi-function"></a><span data-ttu-id="b40af-102">InverseModI 函式</span><span class="sxs-lookup"><span data-stu-id="b40af-102">InverseModI function</span></span>

<span data-ttu-id="b40af-103">命名空間： [Microsoft 量子. 數學](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b40af-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b40af-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b40af-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b40af-105">傳回 $b $，$a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="b40af-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="b40af-106">輸入</span><span class="sxs-lookup"><span data-stu-id="b40af-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b40af-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b40af-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b40af-108">要反轉的數位</span><span class="sxs-lookup"><span data-stu-id="b40af-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="b40af-109">模數： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b40af-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b40af-110">根據數位反轉的模數</span><span class="sxs-lookup"><span data-stu-id="b40af-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="b40af-111">輸出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b40af-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b40af-112">整數 $b $，例如 $a \cdot b = 1 ( \operatorname{mod} \texttt{modulus} ) $。</span><span class="sxs-lookup"><span data-stu-id="b40af-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>