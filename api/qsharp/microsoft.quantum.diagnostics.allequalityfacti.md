---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223879"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="947f9-102">AllEqualityFactI 函式</span><span class="sxs-lookup"><span data-stu-id="947f9-102">AllEqualityFactI function</span></span>

<span data-ttu-id="947f9-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="947f9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="947f9-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="947f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="947f9-105">判斷提示兩個整數值陣列是否相等。</span><span class="sxs-lookup"><span data-stu-id="947f9-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="947f9-106">輸入</span><span class="sxs-lookup"><span data-stu-id="947f9-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="947f9-107">實際： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="947f9-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="947f9-108">由感興趣的測試案例所產生的陣列。</span><span class="sxs-lookup"><span data-stu-id="947f9-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="947f9-109">預期： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="947f9-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="947f9-110">預期來自感興趣之測試案例的陣列。</span><span class="sxs-lookup"><span data-stu-id="947f9-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="947f9-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="947f9-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="947f9-112">如果陣列不相等，則為要列印的訊息。</span><span class="sxs-lookup"><span data-stu-id="947f9-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="947f9-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="947f9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

