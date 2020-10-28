---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 9ccd212010ae557de5ca4ab2a38d4724c5c29aa8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698179"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="4fc26-102">AllEqualityFactI 函式</span><span class="sxs-lookup"><span data-stu-id="4fc26-102">AllEqualityFactI function</span></span>

<span data-ttu-id="4fc26-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4fc26-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4fc26-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fc26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fc26-105">判斷提示兩個整數值陣列是否相等。</span><span class="sxs-lookup"><span data-stu-id="4fc26-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="4fc26-106">輸入</span><span class="sxs-lookup"><span data-stu-id="4fc26-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="4fc26-107">實際： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4fc26-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4fc26-108">由感興趣的測試案例所產生的陣列。</span><span class="sxs-lookup"><span data-stu-id="4fc26-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="4fc26-109">預期： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4fc26-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4fc26-110">預期來自感興趣之測試案例的陣列。</span><span class="sxs-lookup"><span data-stu-id="4fc26-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="4fc26-111">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4fc26-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4fc26-112">如果陣列不相等，則為要列印的訊息。</span><span class="sxs-lookup"><span data-stu-id="4fc26-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4fc26-113">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fc26-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

