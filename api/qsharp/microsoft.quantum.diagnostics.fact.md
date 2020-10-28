---
uid: Microsoft.Quantum.Diagnostics.Fact
title: 事實函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698070"
---
# <a name="fact-function"></a><span data-ttu-id="78178-102">事實函數</span><span class="sxs-lookup"><span data-stu-id="78178-102">Fact function</span></span>

<span data-ttu-id="78178-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="78178-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="78178-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78178-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78178-105">宣告傳統條件為 true。</span><span class="sxs-lookup"><span data-stu-id="78178-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="78178-106">輸入</span><span class="sxs-lookup"><span data-stu-id="78178-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="78178-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="78178-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="78178-108">要宣告的條件。</span><span class="sxs-lookup"><span data-stu-id="78178-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="78178-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="78178-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="78178-110">當傳統條件為 false 時，要列印的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="78178-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78178-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78178-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="78178-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="78178-112">See Also</span></span>

- [<span data-ttu-id="78178-113">Microsoft 量子。衝突</span><span class="sxs-lookup"><span data-stu-id="78178-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)