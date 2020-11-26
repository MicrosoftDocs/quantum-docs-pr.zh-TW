---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 79dcf65956ba9436fb6fdd452f22f35d4852d6f8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213696"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="36cb6-102">AllEqualityFactB 函式</span><span class="sxs-lookup"><span data-stu-id="36cb6-102">AllEqualityFactB function</span></span>

<span data-ttu-id="36cb6-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="36cb6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="36cb6-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36cb6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36cb6-105">判斷提示兩個布林值陣列是否相等。</span><span class="sxs-lookup"><span data-stu-id="36cb6-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="36cb6-106">輸入</span><span class="sxs-lookup"><span data-stu-id="36cb6-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="36cb6-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="36cb6-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="36cb6-108">由感興趣的測試案例所產生的陣列。</span><span class="sxs-lookup"><span data-stu-id="36cb6-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="36cb6-109">預期： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="36cb6-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="36cb6-110">預期來自感興趣之測試案例的陣列。</span><span class="sxs-lookup"><span data-stu-id="36cb6-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="36cb6-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="36cb6-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="36cb6-112">如果陣列不相等，則為要列印的訊息。</span><span class="sxs-lookup"><span data-stu-id="36cb6-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="36cb6-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36cb6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

