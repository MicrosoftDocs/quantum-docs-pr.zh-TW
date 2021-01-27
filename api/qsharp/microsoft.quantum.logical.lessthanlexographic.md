---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 函式
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 716f58b747e9f58c338670271bb2e7aed96fe98c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815651"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="2e559-102">LessThanLexographic 函式</span><span class="sxs-lookup"><span data-stu-id="2e559-102">LessThanLexographic function</span></span>

<span data-ttu-id="2e559-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2e559-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2e559-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e559-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e559-105">用來執行 `LexographicComparison` 。</span><span class="sxs-lookup"><span data-stu-id="2e559-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="2e559-106">輸入</span><span class="sxs-lookup"><span data-stu-id="2e559-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="2e559-107">比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e559-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="2e559-108">左方： t []</span><span class="sxs-lookup"><span data-stu-id="2e559-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="2e559-109">right： t []</span><span class="sxs-lookup"><span data-stu-id="2e559-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="2e559-110">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2e559-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2e559-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="2e559-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e559-112">不要</span><span class="sxs-lookup"><span data-stu-id="2e559-112">'T</span></span>

