---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic 函式
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 360088e31a47a7bb114bc0527edf600cd78740f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697291"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="d0a82-102">LessThanLexographic 函式</span><span class="sxs-lookup"><span data-stu-id="d0a82-102">LessThanLexographic function</span></span>

<span data-ttu-id="d0a82-103">命名空間： [Microsoft 量子. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d0a82-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d0a82-104">包： [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d0a82-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d0a82-105">用來執行 `LexographicComparison` 。</span><span class="sxs-lookup"><span data-stu-id="d0a82-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="d0a82-106">輸入</span><span class="sxs-lookup"><span data-stu-id="d0a82-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="d0a82-107">比較： ( t，t) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d0a82-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="d0a82-108">左方： t []</span><span class="sxs-lookup"><span data-stu-id="d0a82-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="d0a82-109">right： t []</span><span class="sxs-lookup"><span data-stu-id="d0a82-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="d0a82-110">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d0a82-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d0a82-111">類型參數</span><span class="sxs-lookup"><span data-stu-id="d0a82-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d0a82-112">不要</span><span class="sxs-lookup"><span data-stu-id="d0a82-112">'T</span></span>

