---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 函式
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 3b3ac3f9f8b70307099de60899c969abb2acad7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197665"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="81971-102">LessThanLexographic 函式</span><span class="sxs-lookup"><span data-stu-id="81971-102">LessThanLexographic function</span></span>

<span data-ttu-id="81971-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="81971-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="81971-104">封裝： [Microsoft 量子. 標準](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81971-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81971-105">用來執行 `LexographicComparison` 。</span><span class="sxs-lookup"><span data-stu-id="81971-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="81971-106">輸入</span><span class="sxs-lookup"><span data-stu-id="81971-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="81971-107">比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="81971-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="81971-108">左方： t []</span><span class="sxs-lookup"><span data-stu-id="81971-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="81971-109">right： t []</span><span class="sxs-lookup"><span data-stu-id="81971-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="81971-110">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="81971-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="81971-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="81971-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="81971-112">不要</span><span class="sxs-lookup"><span data-stu-id="81971-112">'T</span></span>

