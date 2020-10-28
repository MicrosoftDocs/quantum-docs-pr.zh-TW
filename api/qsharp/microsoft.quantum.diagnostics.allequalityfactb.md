---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698182"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="9b84e-102">AllEqualityFactB 函式</span><span class="sxs-lookup"><span data-stu-id="9b84e-102">AllEqualityFactB function</span></span>

<span data-ttu-id="9b84e-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9b84e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9b84e-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b84e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b84e-105">判斷提示兩個布林值陣列是否相等。</span><span class="sxs-lookup"><span data-stu-id="9b84e-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="9b84e-106">輸入</span><span class="sxs-lookup"><span data-stu-id="9b84e-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="9b84e-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9b84e-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9b84e-108">由感興趣的測試案例所產生的陣列。</span><span class="sxs-lookup"><span data-stu-id="9b84e-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="9b84e-109">預期： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9b84e-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9b84e-110">預期來自感興趣之測試案例的陣列。</span><span class="sxs-lookup"><span data-stu-id="9b84e-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="9b84e-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9b84e-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9b84e-112">如果陣列不相等，則為要列印的訊息。</span><span class="sxs-lookup"><span data-stu-id="9b84e-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b84e-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b84e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

