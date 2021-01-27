---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: a7043b9c670f79e270180c583fef56b70c1a3bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830895"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="721b4-102">AllEqualityFactI 函式</span><span class="sxs-lookup"><span data-stu-id="721b4-102">AllEqualityFactI function</span></span>

<span data-ttu-id="721b4-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="721b4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="721b4-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="721b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="721b4-105">判斷提示兩個整數值陣列是否相等。</span><span class="sxs-lookup"><span data-stu-id="721b4-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="721b4-106">輸入</span><span class="sxs-lookup"><span data-stu-id="721b4-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="721b4-107">實際： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="721b4-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="721b4-108">由感興趣的測試案例所產生的陣列。</span><span class="sxs-lookup"><span data-stu-id="721b4-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="721b4-109">預期： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="721b4-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="721b4-110">預期來自感興趣之測試案例的陣列。</span><span class="sxs-lookup"><span data-stu-id="721b4-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="721b4-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="721b4-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="721b4-112">如果陣列不相等，則為要列印的訊息。</span><span class="sxs-lookup"><span data-stu-id="721b4-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="721b4-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="721b4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

