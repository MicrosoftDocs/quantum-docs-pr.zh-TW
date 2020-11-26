---
uid: Microsoft.Quantum.Diagnostics.Fact
title: 事實函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 74ec020d0437d885d7cbfc98a2c9c0c1867d5d39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201677"
---
# <a name="fact-function"></a><span data-ttu-id="2e673-102">事實函數</span><span class="sxs-lookup"><span data-stu-id="2e673-102">Fact function</span></span>

<span data-ttu-id="2e673-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2e673-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2e673-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2e673-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2e673-105">宣告傳統條件為 true。</span><span class="sxs-lookup"><span data-stu-id="2e673-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2e673-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2e673-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2e673-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e673-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2e673-108">要宣告的條件。</span><span class="sxs-lookup"><span data-stu-id="2e673-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="2e673-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2e673-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2e673-110">當傳統條件為 false 時，要列印的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="2e673-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e673-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e673-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2e673-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2e673-112">See Also</span></span>

- [<span data-ttu-id="2e673-113">Microsoft 量子。衝突</span><span class="sxs-lookup"><span data-stu-id="2e673-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)