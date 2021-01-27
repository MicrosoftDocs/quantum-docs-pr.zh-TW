---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 矛盾函數
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829356"
---
# <a name="contradiction-function"></a><span data-ttu-id="227aa-102">矛盾函數</span><span class="sxs-lookup"><span data-stu-id="227aa-102">Contradiction function</span></span>

<span data-ttu-id="227aa-103">命名空間： [Microsoft 量子. 診斷](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="227aa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="227aa-104">套件： [QSharp Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="227aa-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="227aa-105">宣告傳統條件為 false。</span><span class="sxs-lookup"><span data-stu-id="227aa-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="227aa-106">輸入</span><span class="sxs-lookup"><span data-stu-id="227aa-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="227aa-107">實際： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="227aa-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="227aa-108">要宣告的條件。</span><span class="sxs-lookup"><span data-stu-id="227aa-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="227aa-109">message： [字串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="227aa-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="227aa-110">當傳統條件為真時，所要列印的失敗訊息字串。</span><span class="sxs-lookup"><span data-stu-id="227aa-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="227aa-111">輸出： [單位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="227aa-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="227aa-112">範例</span><span class="sxs-lookup"><span data-stu-id="227aa-112">Example</span></span>

<span data-ttu-id="227aa-113">下列 Q # 程式碼會列印 "Hello，world"：</span><span class="sxs-lookup"><span data-stu-id="227aa-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="227aa-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="227aa-114">See Also</span></span>

- [<span data-ttu-id="227aa-115">Microsoft.. 診斷事實</span><span class="sxs-lookup"><span data-stu-id="227aa-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)