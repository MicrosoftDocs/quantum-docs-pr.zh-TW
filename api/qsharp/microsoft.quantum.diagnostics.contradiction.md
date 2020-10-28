---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 矛盾函數
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698122"
---
# <a name="contradiction-function"></a><span data-ttu-id="37d50-102">矛盾函數</span><span class="sxs-lookup"><span data-stu-id="37d50-102">Contradiction function</span></span>

<span data-ttu-id="37d50-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="37d50-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="37d50-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37d50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37d50-105">宣告傳統條件為 false。</span><span class="sxs-lookup"><span data-stu-id="37d50-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="37d50-106">輸入</span><span class="sxs-lookup"><span data-stu-id="37d50-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="37d50-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="37d50-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="37d50-108">要宣告的條件。</span><span class="sxs-lookup"><span data-stu-id="37d50-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="37d50-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="37d50-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="37d50-110">當傳統條件為真時，所要列印的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="37d50-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37d50-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37d50-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="37d50-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="37d50-112">See Also</span></span>

- [<span data-ttu-id="37d50-113">Microsoft.. 診斷事實</span><span class="sxs-lookup"><span data-stu-id="37d50-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)