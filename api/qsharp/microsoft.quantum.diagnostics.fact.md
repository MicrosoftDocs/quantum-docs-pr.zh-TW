---
uid: Microsoft.Quantum.Diagnostics.Fact
title: 事實函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853312"
---
# <a name="fact-function"></a><span data-ttu-id="49e9c-102">事實函數</span><span class="sxs-lookup"><span data-stu-id="49e9c-102">Fact function</span></span>

<span data-ttu-id="49e9c-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="49e9c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="49e9c-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="49e9c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="49e9c-105">宣告傳統條件為 true。</span><span class="sxs-lookup"><span data-stu-id="49e9c-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="49e9c-106">輸入</span><span class="sxs-lookup"><span data-stu-id="49e9c-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="49e9c-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="49e9c-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="49e9c-108">要宣告的條件。</span><span class="sxs-lookup"><span data-stu-id="49e9c-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="49e9c-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="49e9c-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="49e9c-110">當傳統條件為 false 時，要列印的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="49e9c-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49e9c-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49e9c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="49e9c-112">範例</span><span class="sxs-lookup"><span data-stu-id="49e9c-112">Example</span></span>

<span data-ttu-id="49e9c-113">下列 Q # 程式碼片段將會失敗：</span><span class="sxs-lookup"><span data-stu-id="49e9c-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="49e9c-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="49e9c-114">See Also</span></span>

- [<span data-ttu-id="49e9c-115">Microsoft 量子。衝突</span><span class="sxs-lookup"><span data-stu-id="49e9c-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)