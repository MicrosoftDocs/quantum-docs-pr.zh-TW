---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 矛盾函數
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202136"
---
# <a name="contradiction-function"></a><span data-ttu-id="e1c41-102">矛盾函數</span><span class="sxs-lookup"><span data-stu-id="e1c41-102">Contradiction function</span></span>

<span data-ttu-id="e1c41-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e1c41-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e1c41-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e1c41-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e1c41-105">宣告傳統條件為 false。</span><span class="sxs-lookup"><span data-stu-id="e1c41-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e1c41-106">輸入</span><span class="sxs-lookup"><span data-stu-id="e1c41-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="e1c41-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e1c41-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e1c41-108">要宣告的條件。</span><span class="sxs-lookup"><span data-stu-id="e1c41-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="e1c41-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e1c41-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e1c41-110">當傳統條件為真時，所要列印的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="e1c41-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1c41-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1c41-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e1c41-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1c41-112">See Also</span></span>

- [<span data-ttu-id="e1c41-113">Microsoft.. 診斷事實</span><span class="sxs-lookup"><span data-stu-id="e1c41-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)